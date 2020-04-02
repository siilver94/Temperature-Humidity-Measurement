import java.util.Date;
import java.util.Timer;

public class TimerThread {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("서버 동작 중...");
		while (true) {
			GetJsonData jsonData = new GetJsonData();
			Timer timer = new Timer();

			Date today = new Date();
		//@SuppressWarnings("deprecation")
		//Date current = new Date(today.getYear(), today.getMonth(), today.getDate(), 17, 34, 30); // 시, 분, 초 순서로
			// 작동 시간을 직접 세팅
			//timer.schedule(jsonData, current);
			timer.scheduleAtFixedRate(jsonData, 5000,7200*1000);
		//timer.schedule(jsonData, 5000, 1000 * 10);
			// while을 일정한 시간만큰 돌려야 함으로
			try {
				Thread.sleep(1000 * 3600 * 24 * 4); // 60초 X 60분 X 6시간마다 작동
			} catch (Exception e) {

			}
		}
	}
}
