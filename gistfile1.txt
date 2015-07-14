import android.support.v4.view.MotionEventCompat;
import android.view.MotionEvent;

public class TouchUtils {

	public static int getAction(MotionEvent event) {
		return MotionEventCompat.getActionMasked(event);
	}

	public static int getPointerIndex(MotionEvent event) {
		return MotionEventCompat.getActionIndex(event);
	}

	public static int getPointerId(MotionEvent event) {
		return MotionEventCompat.getPointerId(event, getPointerIndex(event));
	}

	public static int getPointerPosX(MotionEvent event) {
		return (int)event.getX(getPointerIndex(event));
	}

	public static int getPointerPosY(MotionEvent event) {
		return (int)event.getY(getPointerIndex(event));
	}

	public static boolean isUpOrCancelEvent(MotionEvent event) {
		final int action = getAction(event);
		return action == MotionEvent.ACTION_UP ||
				action == MotionEvent.ACTION_POINTER_UP ||
				action == MotionEvent.ACTION_CANCEL;
	}
}