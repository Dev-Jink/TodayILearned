# ReactiveX
[목록(이전)](../ReadMe.md)

ReactiveX는 관찰가능한 sequences를 이용하여, 비동기 와 이벤트에 기반된 프로그래밍의 라이브러리

## 왜 Obserables를 이용해야하는가?
- ReactiveX Observable 모델을 사용하면 배열과 같은 데이터 항목 수집에 사용하는 것과 동일한 종류의 간단하고 구성 가능한 작업으로 비동기 이벤트 스트림을 처리할 수 있습니다.

- ReactiveX Observable은 비동기 데이터의 시퀀스와 플로우를 구성하기 위한 것입니다.

## Observable
ReactiveX에서 옵저버는 Observable을 구독합니다.
Observable에서 어떤 객체가 배출되면, 옵저버에 의해 알림을 받고 처리합니다.
![image](https://reactivex.io/assets/operators/legend.png)

## Reactive와 일반적인 메서드 호출의 차이점
### 일반적인 메서드 호출
```Swift
// 메서드드를 호출후, 리턴 값을 'returnVal'에 할당
let returnVal = someMethod(itsParameters)
// returnVal을 통해 필요한 작업을 진행.
```
### Reactive 호출
```Swift
// 옵저버의 onNext 핸들러를 정의, 실행x
let myfunc = ((Element) -> Void){item in /*필요 연찬 서리*/}
let myErrorfunc = ((Swift.Error) -> Void){error in /*필요 연찬 서리*/}
let myCompletefunc = { /*최종 응답 후 정리 작업*/}
var myObservable = someMethod(itsParameters)
myObservable.subscribe(onNext: myfunc, onError: myErrorfunc, onComplete: myCompletefunc)
// 필요고드 계속 구현
```

## 구독 해지
ReactiveX 구현체중 Subscriber라는 옵저버 인터페이스가 있는데 이는 unsubscribe 역할을 하는 메서드(`dispose()`)를 제공한다. 현재 구독 중인 Observable 중, 옵저버가 더이상 구독을 원치 않을 경우 이 메서드를 통해 구독 해지가 가능하다.

## HotObservable 와 ColdObservable
Hot Observable

	•	정의: 구독 여부와 상관없이 항목을 계속 배출하는 Observable.
	•	특징: 구독자는 구독 시점 이후의 항목만 받는다.
	•	예시: 라이브 방송, 시스템 이벤트 스트림.

Cold Observable

	•	정의: 구독자가 구독을 시작할 때마다 새로운 데이터 스트림을 생성하는 Observable.
	•	특징: 각 구독자는 독립적인 데이터 스트림을 받는다.
	•	예시: 녹화된 비디오, HTTP 요청.
    
## 연산자 체인
대부분의 연산자들은 Observable 상에서 동작하고 Observable을 리턴한다.
Observable 연산자 체인은 원본 Observable과는 떨어져서 동작할 수 없고 순서대로 동작하기 때문에, 호출 체인 중 바로 이전에 호출된 연산자가 리턴한 Observable을 기반으로 실행된다