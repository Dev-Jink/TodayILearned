# ReactiveX
[목록(이전)](../ReadMe.md)

ReactiveX는 관찰가능한 sequences를 이용하여, 비동기 와 이벤트에 기반된 프로그래밍의 라이브러리

## Scheduling
Observable 연산자 체인에 멀티스레딩을 적용하고 싶다면, 특정 스케줄러를 사용해서 연산자(또는 특정 Observable)를 실행하면 된다.

![Scheduling](https://reactivex.io/documentation/operators/images/schedulers.png)