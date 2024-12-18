+++
title = 'Toss Daily Log 2'
date = 2024-12-18T22:39:52+09:00
draft = false
tags = ['recruit']
+++

## 프로젝트의 버그들

아래는 내가 마주한 결함들의 원인들 중 일부이다. 기술적으로 어려운 것은 없지만, 언어의 대한 이해가 부족하다면 예외 상황이 나타나야지만 존재를 알 수 있는 버그들이 많다. 물론 테스트 코드가 예외케이스 별로 잘 짜여져 있으면 미리 잡을 수 있겠지만, 이 프로젝트는 테스트 코드가 없기도 하고, 업무 로직이 상당히 방대하고 복잡하기 때문에 실제로 익셉션이 터지기 전까지는 모를 수도 있다.

### 레거시 javascript 코드를 큰 고민 없이 java로 변환하면서 생기는 버그.

- `substring(int beginIndex, int endIndex)` 함수: 자바스크립트의 함수에서는 `endIndex`가 `beginIndex`보다 작아도 `exception` 없이 넘어가지는 반면, 자바에서는 `IndexOutOfBoundsException`이 던져진다.
- `string`의 `immutability`와 자바의 `StringBuffer`: 레거시 코드를 자바로 전환하면서, 문자열을 생성하는 데 `StringBuffer`를 사용하고 중간 값을 다른 변수에 저장하는 로직이 있었다. 하지만 `StringBuffer.toString()`을 호출하지 않고 그대로 넘겨주는 바람에, `StringBuffer`가 변경될 때마다 저장된 변수들의 값도 함께 변경되는 버그가 발생했다.

위와 같이 언어들간 비슷하면서도 명확하게 다른 면들이 있고 이를 정확히 이해해야 이런 (사실 굉장히 간단한) 버그들을 사전에 모면 할 수 있다.
