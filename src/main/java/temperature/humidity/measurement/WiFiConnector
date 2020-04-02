import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.UnsupportedEncodingException;
import java.util.ArrayList;

public class TcpClient {
public static void main(String[] args) throws UnsupportedEncodingException, IOException {
	connect("Allen"); //"" 안에 와이파이 이름 대소문자 구분해서 그대로 입력
	
	
}
	public static void connect(String wifi) throws UnsupportedEncodingException, IOException {
		for (String i : cmd("netsh wlan connect "+wifi)) {
		System.out.println(i);
		}
		}

		public static ArrayList<String> cmd(String command) throws UnsupportedEncodingException, IOException {
		ArrayList<String> output = new ArrayList<>();
		BufferedReader br = new BufferedReader(
		new InputStreamReader(Runtime.getRuntime().exec(command).getInputStream(), "EUC-KR"));
		String i;
		while ((i = br.readLine()) != null) {
		output.add(i);
		}
		return output;
		}
}

