import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class ConnectDatabase {
	
	public static void insert(double temp, double hum) {
		Connection conn = null;
		PreparedStatement pstmt = null;
				
		try {
			Class.forName("com.mysql.jdbc.Driver");
//useUnicode=true&characterEncoding=utf8&allowPublicKeyRetrieval=true&
			String url = "jdbc:mysql://localhost:3306/esp8266?useSSL=false";
			conn = DriverManager.getConnection(url, "devadmin", "dbpass");

	
			String sql = "INSERT INTO temp_hum (temp,humd,year,md,time) VALUES (?,?,?,?,?)";
			pstmt = conn.prepareStatement(sql);

			SimpleDateFormat year = new SimpleDateFormat("yyyy");
			SimpleDateFormat time = new SimpleDateFormat("HH:mm:ss");
			SimpleDateFormat md = new SimpleDateFormat("MMdd");
			Date current  = new Date();
			
			
			pstmt.setDouble(1, temp);
			pstmt.setDouble(2, hum);
			pstmt.setString(3, year.format(current));
			pstmt.setString(4, md.format(current));
			pstmt.setString(5, time.format(current));
			
			
			int count = pstmt.executeUpdate();
			if (count == 0) {
				System.out.println("데이터 입력 실패");
			} else {
				System.out.println("데이터 입력 성공");
			}
		} catch (ClassNotFoundException e) {
			System.out.println("드라이버 로딩 실패");
		} catch (SQLException e) {
			System.out.println("에러 " + e);
		} finally {
			try {
				if (conn != null && !conn.isClosed()) {
					conn.close();
				}
				if (pstmt != null && !pstmt.isClosed()) {
					pstmt.close();
				}
			} catch (SQLException e) {
				e.printStackTrace();
			}
		}
	}
}
