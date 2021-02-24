# Vulkan Tutorial

## What is Vulkan?

Vulkan은 Khronos group 에서 개발한 Cross-Platform Graphic API다. Vulkan이 OpenGL의 후계자라는 말이 있지만 Vulkan은 기존의 Graphics API (OpenGL 및 DirectX 와 같은) 들과 매우 다르다. 

기존의 Grahpics API (OpenGL 및 DirectX와 같은) 들은 일종의 High-Level API 다. Driver가 해당 API들을 Graphics Hardware에 적합하게 변환 시키는 일을 했기 때문에 개발자들은 굳이 Graphics Hardware의 (매우 복잡한) 세부 사항들을 알 필요가 없었다.

하지만 Application의 기능이 고도화 됨에 따라, 이러한 [편의성 및 안정성] 보다 그로 인해 발생하는 [Overhead와 Performance의 하락]에 더 신경을 쓰게 되었고, 이에 따라 개발자들은 더 높은 성능을 위해 저수준 (Low-Level)의 Hardware access를 요구하게 되었다.

Vulkan은 기본적으로 이러한 High-Level API가 갖을 수 있는 높은 Overhead를 피하기 위해서 명시적 (Explicit)인 API로 설계 되었다. Vulkan 개발자는 기존에 Driver가 자동으로 수행해주던 많은 기능들을 모두 직접 처리해야 한다.

가령, OpenGL과 같은 API들은 개발자에 의해 생성된 객체의 상태, 버퍼 메모리 관리 및 동기화 등을 드라이버에서 자동으로 체크하고 관리해준다. 이는 예외 상황에서 Application의 안정성을 높여주지만 반대로 정상적인 상황에서는 CPU자원을 낭비하는 일이 될 수 있다. Vulkan은 이러한 내용 (위에서 언급한 객체의 상태 추적, 버퍼 메모리 관리 및 동기화 등)을 모두 개발자에게 위임한다. 

이로 인해서 개발자가 처리해야 할 일이 매우 많아진다. 또한 잘못된 API 사용에 의해 Application이 예상치 못한 종료를 하는 것도 모두 개발자의 책임이 된다. 이러한 단점에도 불구하고 프로그램 자원 (Application Resources)과 Graphics Hardware를 효율적으로 관리할 수 있기 때문에 기존의 Graphics API들 보다 높은 성능을 제공할 수 있다.

## About this Tutorial

해당 Tutorial은 어떻게 하면 Vulkan Application을 만들 수 있는지 알아보는데 중점을 맞췄다.
우선 최적화 등의 모든 부분을 제외하고 가장 간단한 Vulkan Application을 만들기 위해서 필요한 최소한의 과정을 보여줄 것이다. **(다만, 이 최소한의 과정이 매우 길다...)**

이 후에 약간의 최적화 이슈에 대해서 이야기 한 후에 Uniform Buffer, Vertex Buffer, Texture 등으로 점점 확장해 나가고자 한다.

**p.s.1** 해당 Tutorial의 전반부는 Vulkan SDK에 포함되어 있는 Tutorial 항목을 참조했다.

**p.s.2** 해당 Tutorial은 Windows, Ubuntu, MacOS 를 기준으로 작성되었다

**p.s.3** 해당 Tutorial에 사용된 코드는 다음 환경에서 확인되었다.
   * Vulkan Version - 1.1.xx 버전에서 테스트
   * OS별 개발환경
      - Windows 10   - Visual Studio 2015, Visual Studio 2017
      - Ubuntu 18.04 - gcc 5.4.0
      - MacOS 10.14  - Xcode 10 (both cocoa bundle & command line tool)
