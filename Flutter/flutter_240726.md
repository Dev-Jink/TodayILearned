- Flutter는 프레임워크
- 사용자 인터페이스와 애플리케이션을 만들기 위해 사용
- 앱 개발을 위한 프로그래밍 언어로는 Dart 사용
- 크로스 플랫폼(안드로이드, IOS) 애플리케이션 개발
- 인터페이스나 사용자 경험을 하나로 통일

---

## Widget

1. 독립적으로 실행되는 작은 프로그램
2. 주로 바탕화면 등에서 날씨나 뉴스, 생활정보 등을 보여줌
3. 그래픽이나 데이터 요소를 처리하는 함수를 가지고 있음

in flutter?

1. UI를 만들고 구성하는 모든 기본 단위 요소
2. 눈에 보이지 않는 요소들까지 위젯

### Type of Widgets

1. Stateless Widget(상태가 없는 정적인 위젯)
    1. 스크린상에 존재만 할 뿐 아무것도 하지 않음
    2. 어떠한 실시간 데이터도 저장하지 않음
    3. 어떤 변화(모양, 상태)를 유발시키는 value값을 가지지 않음
2. Stateful Widget(계속 움직임이나 변화 있는 위젯)
    1. 사용자의 interaction에 따라서 모양이 바뀜
    2. 데이터를 받게 되었을 때 모양이 바뀜
3. Inherited Widget

1. Stateful ⇒ value 값을 지속적으로 추적 보존
2. Stateless ⇒ 이전 상호작용의 어떠한 값도 저장하지 않음

### Flutter Widget tree

1. Widget들은 tree 구조로 정리될 수 있음
2. 한 Widget내에 얼마든지 다른 widget들이 포함될 수 있음
3. Widget은 부모 위젯과 자식 위젯으로 구성
4. Parent widget을 widget container라고 부르기도 함

트리구조

[root]

- [App]
    - MaterialApp
        - MyHomePage
            - Scaffold
                - Center
                    - Column
                - AppBar

### BuildContext

- widget tree에서 현재 widget의 위치를 알 수 있는 정보
- BuildContext는 stateless위젯이나 state 빌드 메서드에 의해서 리턴된 위젯의 부모가 된다.