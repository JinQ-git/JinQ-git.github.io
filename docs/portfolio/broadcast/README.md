# SK BTV Mobile (Oksusu)

1. Live 및 VoD HLS 서버 제작
   - 초기 목표는 서버당 약 1000명 처리 -> 스트레스 테스트에서는 약 900여명 까지 테스트
   - 실제 운영단계에서는 서버당 400명 미만으로 운영됨 (평균 200여명)

1. 스트림 관리 웹페이지 제작
   - 웹페이지를 통해 (live 채널) 스트림을 추가 / 제거 할 수 있게 구현

## 주요 작업

* HLS protocol 처리 모듈
* 수동 Session 관리 모듈
* 컨텐츠 암호화 모듈
* MP2TS - IFrame 정보 추출 모듈
* HLS 스트레스 테스트용 클라이언트 시뮬레이터
* (윈도우즈용) 동작확인을 위한 HLS 플레이어 개발

## 개발 환경

### HLS 서버

- lighttpd + php(fastcgi)

### IFrame 정보 추출 프로그램

- Cross platform, Console application
- C/C++

### HLS 스트레스 테스트 시뮬레이터

- Windows
- MFC
- C++

### HLS 동작 확인용 플레이어

- Windows
- WINAPI
- OpenGL 2.x
- DirectSound 8
- FFmpeg(avcodec, avformat, swresample)

 ---

# Cable 방송 향 VoD 시스템 개발

AMS (Asset management system) 개발

> CMB(한강방송), GBN(강원방송)에서 운영

## 주요 작업

* [Metadata](https://www.cablelabs.com/specifications/cablelabs-video-on-demand-content-specification-version-1-1) 파싱 & 운영 사이트에 맞게 가공
* Metadata DB 설계 및 구축; MySQL
* 영상파일(MP2TS)로부터 정보(IFrame 등) 추출
* (CMB 한정) 중앙서버에서 지방 컨텐츠 스토리지 서버로 컨텐츠 재배포; Bandwidth 제한 기능

## 개발 환경

- Cross platform; Console application
- C/C++
- libxml2
- live555; MP2TS 정보 추출
- MySQL
