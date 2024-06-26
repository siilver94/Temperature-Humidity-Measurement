# Project : Temperature and Humidity Measurement

<code><img height = "400"
src = https://github.com/siilver94/Temperature-Humidity-Measurement/assets/57824945/b254f376-8def-4a28-b4a9-46cbe51900eb></code>


## 프로젝트 소개

이번 프로젝트는 모바일 앱을 개발하고, 개발한 앱을 통하여 무선통신 으로 해당 온/습도 센서가 있는 구역의 온/습도 측정 수치를
편리하게 어디서든 확인하는 것이 목적입니다.

<br/>

## 프로젝트 구조

휴대폰 어플을 개발하기 위해 어플 개발 프레임워크 중 **HybridAPP**형태의 개발 프레임워크인 **Flutter** 를 사용하여 앱을 개발합니다.

**Java(Eclipse)** 로 **소켓통신** 을 하기위해 포트포워딩 방식으로 네트워크 서버를 구축합니다.
구축된 서버와 앱이 설치된 휴대폰이 서로 통신 하기 위해 네트워크를 서로 연결/연동하고 **Arduino** 또한 연결/연동 합니다.

**Arduino**와의 통신은 **ESP8266** 무선(Wifi)으로 통신합니다.

데이터의 통신(Request, Response)은 **RestAPI** 형식으로 데이터를 주고 받습니다.

#### 예)

- localhost:8080/device/sensor/on             (센서를 켜라.)
- localhost:8080/device/sensor/off            (센서를 꺼라.)

<br/>

## 프로젝트 필요 기술

- 앱 개발 (UI형태: `hybridAPP` or `native`(java,코틀린)
- `Arduino nodeMCU-ESP8266 Wifi network sensor`
- `restAPI`
- `Arduino DHT11 온습도 센서`


**앱개발 IDE** : `flutter` / `react-native` / `native script` + `vue.js`

**미들웨어** : `JAVA` - 이클립스 [ 외부jar : rxtx (자바로 아두이노와 시리얼 통신하기 위해 사용) , ]

**아두이노** : `nodeMCU` - ESP8266 [WIFI]

<br/>

## Check list

- PC와 아두이노 와이파이(ESP8266)을 연결하여 통신이 가능한지 - 포트 포워딩 방식.

- PC와 ESP를 분리하여 같은 네트워크 상에서 원격으로 데이터 값을 받을 수 있는지.

- esp8266 과 자바 연동(시리얼,비동기식) 데이터 값을 JSON형태로 받아오기.

- 자바와 Computer Server(DB)와 연동  - 후에 쓰레드로 지정시간마다 값받기.

- 어플 개발 후 아두이노 ↔ 폰 ↔ DB   

<br/>

## 리뷰

우리에겐 간단해 보이는 작은 서비스 일지라도 많은 것들이 연동되어 있다는 것을 알 수 있었습니다.
간단하지만 처음으로 **네트워크(통신)**, **프론트엔드(앱)**, **백앤드(데이터베이스)** 그리고 **제어(아두이노)** 를 사용하여 **Full Cycle** 개발을 해 보았습니다.

이전까지는 데이터베이스만 연동 한다던지, 혹은 아두이노를 통해 센서 값 등을 메인서버(JAVA)에서 출력만 해 보았지만 처음으로 통신의 중요함과 어려움을 배웠고 **포트포워딩** 방식을 통해 **Port** 의 개념에 대해서 이해할 수 있었습니다.

**아두이노**의 센서와도 다양한 방법으로 통신할 수 있었는데 무선 통신 방식을 채택하고 처음으로 센서값들이 메인서버(JAVA)에 출력 됐을때 큰 쾌감을 느꼇습니다.

어플 개발로는, 요즘 엄청난 주가를 달리고있는 크로스플랫폼 개발 프레임워크인 **Flutter**로 앱을 개발하려 했지만
그 당시 오픈코드가 부족하고 아무래도 **JAVA** 가 익숙하여 안드로이드 스튜디오로 기본적인 어플을 만들었습니다
처음으로 어플을 개발해 보면서 생각보다 간단하고 만들기 간편하게 돼 있다는 것도 알게 되었습니다.

**아두이노**를 통하여 **IOT(사물인터넷)** 란 어떻게 동작하는지에 대해 배웠고 **스마트팜**, **스마트 팩토리**등 사물인터넷 이라는 말만 들었었지만, **Ubiquitous** 시대가 곧 멀지 않았고 인지 하지 못했지만 지금도 이미 그런 세상에 살고 있다는 것을 깨달았습니다.
