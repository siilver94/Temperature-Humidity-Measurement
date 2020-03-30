//해당 DB 에 잇는 데이터를 JSON 으로 변환
//http://localhost/esp8266/phpinfo.php    or 192.168.18.204:90/esp8266/phpinfo.php 

<?php
header('Content-Type: text/html; charset=utf8');

$link=mysqli_connect("localhost","allen","203505", "esp8266" );
if (!$link)
{
    header('Content-Type: text/html; charset=euc-kr');
    echo "MySQL 접속 에러 : ";
    echo mysqli_connect_error();
    exit();
}


mysqli_query($link, "set names utf8");

$sql="select * from temp_hum";

$result=mysqli_query($link,$sql);
$data = array();
if($result){
    
    while($e=mysqli_fetch_assoc($result))
        $data[]=$e;
        
        $json = json_encode($data, JSON_PRETTY_PRINT+JSON_UNESCAPED_UNICODE);
        echo $json;
        
}
else{
    echo "SQL문 처리중 에러 발생 : ";
    echo mysqli_error($link);
}



mysqli_close($link);


?>

