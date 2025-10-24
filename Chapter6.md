# 6. Experience and Evaluation

6장은 사실 정리하는 장으로 짧고 빠르게 정리하려고 합니다.

## 6.1 Standardizing the Web

웹이 90년대 이후로 폭발적으로 성장하였으나, 설계 원칙이 일관되지 않아 혼란이 있었습니다.

REST의 목적은 이러한 설계 표준을 확립하는 것이었고, 목표는 **웹이 성장하면서도 구조적 일관성을 잃지 않는 것**이었습니다.

## 6.2 REST Applied to URI

URI는 리소스 식별자로 정의되어, 리소스의 위치가 아닌 **정체(identity)**를 나타내야 했습니다.

URI는 
  
  리소스의 이름만 나타내고
  
  행위를 포함하지 않으며
  
  리소스는 변해도 URI의 의미는 안정되어야 한다
  
는 원칙을 제시하였습니다.

## 6.3 REST Applied to HTTP

REST의 제약조건은 계속 강조하듯이

  client-server, stateless, cache, uniform interface, layered system, code-on-demand

여기서 멱등성이라는 개념을 강조하는데, 멱등성이란 여러 번 호출해도 결과가 같은 것을 의미합니다.

  GET, PUT, DELETE는 멱등해야하며 POST는 매번 멱등하지 않다.

## 6.4 Technology Transfer

REST는 실제 구현에 전이가 가능한 아키텍처이며, 이론이 아닌 실제 오픈소스로 검증된 **설계 철학**임을 강조합니다.

## 6.5 Architecture Lessons

필딩은

  1. 단기 성능보다는 구조적 일관성을
  2. 명확한 인터페이스가 확장성을
  3. 멱등성은 신뢰성을
  4. 하이퍼미디어는 미래 확장성을(물론 이건 현재 react가 등장하면서 달라졌습니다.)
  5. 완벽하게 REST 구현하기는 힘들지만, 방향성만으로도 효과적

임을 강조합니다.

규칙이 아닌, 진화 가능한 방향으로 제시하는 **원리**라고 밝힙니다.
