# ReactiveX
ReactiveX는 관찰가능한 sequences를 이용하여, 비동기 와 이벤트에 기반된 프로그래밍의 라이브러리
## Subject
Subject는 옵저버나 Observable처름 행동하는 ReactiveX의 구현체에서 사용 가능한 일종의 프록시역할

Subject는 옵저버로써 하나이상의 observable을 구독할수 있고, 동시에 Observable이기도하다. 따라서 항목들을 거치면서 재배출하고 옵저빙하며 새로운 항복을 배출할 수 있다.

### Kind of Subject
subject 4종류
#### 1. AsyncSubject
AsyncSubject는 소스 Observable로부터 배출된 마지막 값만 배출하고 소스 Observable의 동작이 완료된 후에 동작

맨 마지막 값을 뒤 이어 오는 옵저버에 전달, 오류로 인해 종료될경우 오류를 그대로 전달.
![AsyncSubject](https://reactivex.io/documentation/operators/images/S.AsyncSubject.png)
![AsyncSubject](https://reactivex.io/documentation/operators/images/S.AsyncSubject.e.png)

#### 2. BehaviorSubject
옵저버가 BehaviorSubjectfmf 구독하기 시작하면, 옵저버는 소스 Observable이 가장 최근에 발행한 항목(또는 아직 아무 값도 발행되지 않았다면 맨 처음 값이나 기본값)의 발행을 시작하며, 그이후 소스 Observable에 의해 발행된 항목을 계속 발행

오류때문에 종료되면 아무런 항목도 배출하지 않고 오류를 전달.
![BehaviorSubject](https://reactivex.io/documentation/operators/images/S.BehaviorSubject.png)
![BehaviorSubject](https://reactivex.io/documentation/operators/images/S.BehaviorSubject.e.png)

#### 3. PublishSubject
PublishSubject는 구독 이후에 소스 Observable이 배출한 항목들만 옵저버에게 배출한다.

구독을 시작한 시점에서 그사이에 배출되는 항목들을 잃어 버릴 수 있다는 단점이 있다

만약, 소스 Observable이 오류 때문에 종료되면 PublishSubject는 아무런 항목도 배출하지 않고 소스 Observable에서 발생한 오류를 그대로 전달한다.
![PublishSubject](https://reactivex.io/documentation/operators/images/S.PublishSubject.png)
![PublishSubject](https://reactivex.io/documentation/operators/images/S.PublishSubject.e.png)

#### 4. ReplaySubject
ReplaySubject는 옵저버가 구독을 시작한 시점과 관계 없이 소스 Observable(들)이 배출한 모든 항목들을 모든 옵저버에게 배출한다.

![ReplaySubject](https://reactivex.io/documentation/operators/images/S.ReplaySubject.png)
