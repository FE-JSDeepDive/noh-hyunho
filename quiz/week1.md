# 1. 호이스팅이 무엇이고 왜 일어날까요??

A. 변수와 함수가 초기화 되기 전 해당 스코프의 최상단으로 끌어 올려지는 현상

> let, const도 호이스팅 되지만 초기화 전에 접근이 불가능하다
> (접근 시 Reference Error 발생)

-> 호이스팅 현상으로 인해 발생한 코드의 예측 가능성 문제를 해결하기 위해 접근을 불가능하게 막았다

# 2. JS는 인터프리터 언어인데 어떻게 호이스팅 현상이 일어나나요?

A. JS엔진은 코드 실행을 위해 `파싱`과 `실행` 두가지 단계를 거치는데 `파싱` 단계에서 호이스팅 처리 뿐 아니라 구문 트리, 실행 컨텍스트를 생성하는 작업도 처리하기 때문이다.

일반적인 인터프리터 언어 --> 런타임에서 한줄 씩 읽는 것

# 3. 왜 변수와 달리 함수만 초기화 과정까지 호이스팅 될까??

A. function으로 작성된 함수의 경우 선언과 초기화, 할당를 동시에 진행하기 때문이다

변수는 **선언만** 호이스팅 되지만 함수는 **선언과 초기화** 모두 호이스팅 된다

-> 그래서 함수는 초기화 전에 호출해도 정상 작동 (function 키워드로 작성된 경우만)
