# Computer Graphics Portfolio

### 목차

1. [Point View](#point-view)
1. [Web Point View](#web-point-view)
1. [Mobile 데모](#mobile-데모)
1. [과제: 차세대 모바일 3D UI Framework 및 Widget 개발](#인크로스-itsoc-과제-차세대-모바일-3d-ui-framework-및-widget-개발)

---

# Point View

Point Cloud로부터 Geometry 정보를 추출하는 프로그램

## 주요 업무

OpenGL 1.0 프로그램을 Modern OpenGL로 업그레이드

- Remove `GLU` features; _view control_, _draw primitive mesh_ and so on.
- Design & implementation a new rendering pipeline, specialized for the point cloud and 5 types of primtive as wireframe; plane, sphere, cylinder, cone, torus
- Implementation math library specialized for computer graphics; view transform, model transform and so on.

## Reference

![](img/fig01_pointview.png)

---

# Web Point View

[Point View](pointview.md) 의 웹버전

## 주요 업무

* 서버 Backend 처리 모듈 담당 ( JavaEE - WAS, Pipe )
* 클라이언트 Frontend UI / UX 설계 및 구현 ( HTML5, Javascript ES6, ajax )
* WebGL 프레임워크 설계에만 참여
* 서버 - 클라이언트 간 프로토콜 설계 및 구현
* Picking 알고리즘 업데이트
* xyz(point cloud) 및 obj 파일 파서 개발

## Reference

[https://developers.curvsurf.com/WebDemo](https://developers.curvsurf.com/WebDemo)

_click thumbnail to watch youtube video_

[![Web Point View](https://i.ytimg.com/vi/jWrk_zz9xX4/hqdefault.jpg?sqp=-oaymwEcCPYBEIoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDKlNfv3lvQjcnbgYzfDWHU8ofeeQ)](https://youtu.be/jWrk_zz9xX4?si=sqXvq2Yd5u0NVaQi)

[![Web Point View - Initial Version](https://i.ytimg.com/vi/oKlxI2r2oWU/hqdefault.jpg?sqp=-oaymwEcCPYBEIoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLD6wFFAPOJmNEcCGvzV1Hf5xJfYpw)](https://youtu.be/oKlxI2r2oWU?si=vrZwAIydJojVboQH)

---

# Mobile 데모

실시간 기하정보 추출 및 증강현실 시각화 데모:

1. Google Project Tango
1. Intel Realsense + Windows Laptop
1. Google ARCore
1. Apple ARKit + LiDAR
1. Microsoft HoloLens 1/2

## 주요 업무

* 각 기기별 렌더링 엔진 설계 및 구현; Modern OpenGL, D3D11, Metal
* Custom Geometry Processing: [Solid WireFrame(Nvidia)](https://developer.download.nvidia.com/SDK/10/direct3d/Source/SolidWireframe/Doc/SolidWireframe.pdf) 응용; _Google Project Tango 및 HoloLens 시리즈 제외_
* Custom 3D graphcis math library 구현
* Vertex Shader를 이용 Raw RGB/D Stream 으로부터 colored point cloud 추출 기능 구현; _iOS + LiDAR 한정_
* 3D feature point로부터 통계학에 근거한 상대적으로 안정적인 point cloud 데이터 추출 기능 구현; _ARKit, ARCore 한정_

## Reference

_click thumbnail to watch youtube video_

### Google Project Tango

[![Google Project Tango](https://i.ytimg.com/an_webp/8ruiudETvuY/mqdefault_6s.webp?du=3000&sqp=CIiLo60G&rs=AOn4CLD_9ozlA3S3Wtf5kxV_Wy5zjWkClA)](https://www.youtube.com/watch?v=8ruiudETvuY)

### Intel RealSense

[![RealSense](https://i.ytimg.com/an_webp/HGwojt6Gqrc/mqdefault_6s.webp?du=3000&sqp=CKedo60G&rs=AOn4CLCn2Du5s0wdxeWxgOwbnsQvjWXUHQ)](https://www.youtube.com/watch?v=HGwojt6Gqrc)

### Google ARCore

[![ARCore 01](https://i.ytimg.com/vi/p2mkBKEp0_U/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLB-DnnFTkdyG93ZWzVkaka9jxVtIg)](https://youtu.be/p2mkBKEp0_U?si=hyPEVaYhkIP5EU-Q)

[![ARCore 02](https://i.ytimg.com/vi/EqQuSTjVL18/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLB1jEhBnmX6daJHt9P1cClPTsoHhg)](https://youtu.be/EqQuSTjVL18?si=6peCgVK3a5lRmUOd&t=30)

### Apple ARKit without LiDAR

[![ARKit](https://i.ytimg.com/vi/PkHjW68JMHQ/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDAOTv7jWNZ96jODAGRVUApqDEdxg)](https://youtu.be/PkHjW68JMHQ?si=W2Uf6tIF0eSCV_N2)

### Apple ARKit with LiDAR

[![ARKit LiDAR](https://i.ytimg.com/an_webp/Pq55xNtvbzQ/mqdefault_6s.webp?du=3000&sqp=CNCWo60G&rs=AOn4CLDBKmOVlOR7gLbXhhTTz_k7Mq5IxQ)](https://www.youtube.com/watch?v=Pq55xNtvbzQ)

[![ARKit LiDAR AR](https://i.ytimg.com/an_webp/eSGY49ND6dY/mqdefault_6s.webp?du=3000&sqp=CJqio60G&rs=AOn4CLATxolIMIweyCDBuiBufMuP9DY7yg)](https://www.youtube.com/watch?v=eSGY49ND6dY)


### HoloLens 1 - with Spatial Mesh Vertices

[![HoloLens](https://i.ytimg.com/an_webp/4RYMR8i8suU/mqdefault_6s.webp?du=3000&sqp=CMejo60G&rs=AOn4CLBFkVWMvbjORil7uGnMAG6llAMZnQ)](https://www.youtube.com/watch?v=4RYMR8i8suU)

[![HoloLens AR](https://i.ytimg.com/vi/_Cao7bVZAMg/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDPqqEdMOoLoKse9yXWkcJRLZWOwA)](https://www.youtube.com/watch?v=_Cao7bVZAMg)

### HoloLens 2 - with Raw Depth Stream

[![HoloLens2](https://i.ytimg.com/an_webp/IDrfxeHuZVo/mqdefault_6s.webp?du=3000&sqp=CPqmo60G&rs=AOn4CLB_dNf23Dmi66VGdFiB2Dum5bGGxw)](https://www.youtube.com/watch?v=IDrfxeHuZVo)

---

# 인크로스 ITSOC 과제: 차세대 모바일 3D UI Framework 및 Widget 개발

UX 기획안에 맞추어 **인크로스**에서 제공한 3D-asset을 활용, 홈 UI 데모 (1차년도), 앱 및 Widget 데모 (2, 3차년도) 프로그램 작성

* Android / Windows 향 OpenGL ES 컨텍스트 위에 개발
* 3D-Asset 엔진은 제공; File Load, Animation Update, Draw Call

## 주요 업무

- 홈 UI 데모를 위한 Framework 설계 및 구현
   * UI Rendering 엔진 설계 및 구현; Scene Graph Node 응용
   * Android / Windows 용 Gesture Event Handler 설계 및 구현; Tap(Click), Double tap, Long tap, Flick, Slide, Pinch in/out
   * 홈 UI 기본 기능 구현; 앱(아이콘)/위젯의 추가, 편집 및 삭제
- 3D UX 앱 및 Widget 데모 구현; 시계 위젯, 메모 앱 / 위젯, 캘린더 앱 / 위젯, 갤러리 앱 / 위젯

## Reference

### 홈 UI 데모

#### 홈 UI 시나리오 1

| | |
|:---:|:---:|
| ![](img/itsoc/s01_fig01.png) | ![](img/itsoc/s01_fig03.png) |
| ![](img/itsoc/s01_fig02.png) | ![](img/itsoc/s01_fig04.png) |
| | |

#### 홈 UI 시나리오 2

| | |
|:---:|:---:|
| ![](img/itsoc/s02_fig01.png) | ![](img/itsoc/s02_fig04.png) |
| ![](img/itsoc/s02_fig02.png) | ![](img/itsoc/s02_fig05.png) |
| ![](img/itsoc/s02_fig03.png) | ![](img/itsoc/s02_fig06.png) |
| | |

### 앱 / 위젯 데모

#### 메모 앱

![](img/itsoc/memo_app_fig01.png)

#### 메모 위젯

![](img/itsoc/memo_widget_fig01.png)

#### 캘린더 앱

| | |
|:---:|:---:|
| ![](img/itsoc/calander_app_fig01.png) | ![](img/itsoc/calander_app_fig02.png) |
| ![](img/itsoc/calander_app_fig03.png) | ![](img/itsoc/calander_app_fig04.png) |
| ![](img/itsoc/calander_app_fig05.png) | ![](img/itsoc/calander_app_fig06.png) |
| | |

#### 캘릭더 위젯

![](img/itsoc/calander_widget_fig01.png)

#### 갤러리 앱

| | |
|:---:|:---:|
| ![](img/itsoc/gallary_app_fig01.png) | ![](img/itsoc/gallary_app_fig02.png) |
| | |

#### 갤러리 위젯

| | |
|:-:|:-:|
| ![](img/itsoc/gallary_widget_fig01.png) | ![](img/itsoc/gallary_widget_fig02.png) |
| | |

---
