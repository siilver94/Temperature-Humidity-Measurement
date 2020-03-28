# Project : Temperature and Humidity Measurement

## 프로젝트 소개

본 프로젝트의 목적은 모바일 앱을 사용하여 무선통신(Wifi)
을 통하여 온/습도 센서가 있는 해당 구역의 온/습도 측정 수치를
편리하게 어디서든 확인하는 것이 목적입니다.


## 프로젝트 구조

휴대폰으로 조작을 하기 위해 휴대폰 UI형태중 **HybridAPP**형태의 모바일 앱 개발 프레임워크인 **Flutter** 를
사용하여 앱을 만듭니다.

**Java(Eclipse)** 를 사용하여 앱이 설치된 휴대폰과 통신 하기 위해 네트워크를 서로 연결/연동하고 또한 온습도
센서를 실질적으로 제어할 **Arduino** 와 연결/연동 합니다.

**Arduino**와의 통신은 무선(Wifi)으로 통신합니다.

데이터의 통신(Request, Response)은 **RESTful** 하게 데이터를 주고 받습니다.

#### 예)

- localhost:8080/device/sensor/on
- localhost:8080/device/sensor/off


## 프로젝트 필요 기술

- 폰 (UI형태: hybridAPP or native(java,코틀린)
- Arduino nodeMCU-ESP8266 Wifi network sensor
- restAPI
- Arduino DHT11 온습도 센서
