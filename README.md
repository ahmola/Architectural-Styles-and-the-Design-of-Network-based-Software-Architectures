# Architectural-Styles-and-the-Design-of-Network-based-Software-Architectures
  
  REST의 개념을 최초로 제시한 로이 필딩의 논문에 대해서 정리한 부분입니다.

## 논문의 목적

로이 필딩은 "웹이 왜 이렇게 설명했는가?"를 실제 설계 경험을 바탕으로 아키텍처적 제약을 이론적으로 확립하기 위해서 작성한 논문입니다.

논문은 1-3장까지 배경과 문제를 정의하고 4장에서는 아키텍처 스타일의 정의와 분류, 5장은 REST 제안, 6장은 REST 적용과 검증, 7-8장은 관련 연구 및 요약


## REpresentational State Transfer

REST의 핵심은 **확장성과 독립성**을 위한 **제약**이라는 것입니다.

REST의 구성요소는 다음과 같습니다.

  - Resource: 모든 정보의 개념적 대상(ex. /user/1, /posts 등의 uri나 "인기있는 게시물" 등 실제로 사용자가 원하는 정보)
  - Representation: 리소스의 현재 상태를 표현한 데이터(ex. JSON, XML, HTML 등 실제로 데이터를 사용자에게 보여지는 형식)
  - Resource Identifier: 리소스를 식별하는 방식(ex. URI 등 실제 리소스를 요청할 때 쓰이는 방식)
  - Connector: 컴포넌트 간 통신 매개체(HTTP, FTP 등)
  - Component: 실제 행위를 수행하는 아키텍처 요소(ex. Client, Server, Gateway, Cache, Proxy 등)

REST의 제약조건은 다음과 같습니다.

  - Client-Server: UI와 데이터 처리의 역할 분리, 관심사 분리와 확장성 향상
  
  - Stateless: 요청 상태 비보존. 서버 확장, 캐시 단순화
  
  - Cacheable: 응답의 캐시 여부를 표시하여 캐싱. 네트워크 효율 향상
  
  - Uniform Interface: 표준화된 인터페이스로 단순성과 호환성 향상
  
  - Layered System: 중간 계층(Proxy, Gateway 등)을 둬서 보안과 확장성 향상
  
  - Code-on-Demand: 서버가 실행 코드 전송: 유연성을 향상 시킴. 논문 발표 당시에는 optional이였으나, 현재는 react의 등장으로 사실상 필수(ex. 크롬 브라우저가 웹 서버에 요청 -> 개발자 도구의 HTML 웹 문서를 다운)

여기서 세부적으로 필딩은 Uniform Interface의 원칙에 대해서 다음과 같이 기술합니다.

  - Identification of Resources: 리소스의 URI로 식별
  
  - Manipulation via Representations: 표현을 통한 조작
  
  - Self-Descriptive Messages: 메시지는 자기 기술적(stateless), 즉 요청에 관한 모든 정보가 들어가야 함
  
  - HATEOAS(react의 등장으로 사실상 쓰지 않음): 하이퍼미디어를 통한 상태 전이 

## REST의 핵심 철학

  서버는 상태를 저장하지 않고, 클라이언트가 리소스의 표현을 통해 애플리케이션 상태를 전이한다.

  - 서버는 리소스 상태를,
  - 클라이언트는 애플리케이션 상태를 관리
  - 상태 전이는 하이퍼링크나 요청으로 수행

REpresentation(표현, JSON이나 HTML 등)으로 State(앱과 리소스의 현재 상태)를 Transfer(전송)

필딩은 웹이 이러한 REST 아키텍처 스타일을 **무의식적**으로 따랐기 때문이라고 주장합니다.

## 결론

제약을 통해 속성이 도출되고 속성이 아키텍처의 품질을 결정하게 된다고 주장합니다.

주의할 점은, 속성은 항상 trade-off이므로 아키텍처 설계자가 요구사항을 고려하여 최선의 속성을 고르는 것이 중요하다고 말합니다.

단일 기술이 아닌 구조적 원리의 중요성을 강조하며, REST는 이러한 원리의 추상화라고 정의합니다.

  - 기술보다는 구조가 우선이다. 왜냐면 기술은 변해도 아키텍처 원리는 남기 때문

  - 제약으로부터 구조적 자유와 유연성이 발현되어 시스템의 복잡도를 감당할 수 있게 된다. 예를 들어, REST는 요청을 CRUD로 제한하여 다양한 환경에서 유연하게 적용하게됨

  - 상태는 클라이언트가 감당한다. 서버가 수 많은 클라이언트의 상태(또는 세션)을 관리하게 되면 부하가 커지며 확장성이 떨어지기 때문

  - 인터페이스는 동일해야 한다. 사실상 제약과 이어지는 내용으로 시스템과 컴포넌트 간 의존성을 줄이는 역할을 한다.

  - 진화에 개방적인 구조여야 한다. 정답이 아닌 방향성이 기준이 되어야 한다.
