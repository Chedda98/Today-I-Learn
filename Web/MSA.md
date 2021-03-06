# MSA (MicroService Architecture)란?

```
"하나의 큰 어플리케이션을 여러개의 작은 어플리케이션으로 쪼개어 변경과 조합이 가능하도록 만든 아키텍쳐"
마치 레고에서 작은 조각들을 합쳐 큰 레고를 만드는 과정이라고 할 수 있다.
```

<br>

## MSA 등장 배경

### `Monolithic Architecture`

```
소프트웨어의 모든 구성요소가 한 프로젝트에 통합되어있는 형태이다.
```

아직까지는 많은 소프트웨어가 Monolithic 형태로 구현되어 있고, 소규모 프로젝트에는 Monolithic Architecture가 훨씬 합리적이다. 간단한 Architecture이고, 유지보수가 용이하기 때문이다.

하지만 일정 규모 이상의 서비스, 혹은 수백명의 개발자가 투입되는 프로젝트에서 Monolithic Architecture은 뚜렷한 한계를 보인다.


- 서비스/프로젝트가 커지면 커질수록, 영향도 파악 및 전체 시스템 구조의 파악에 어려움이 있다.
- 빌드 시간 및 테스트시간, 그리고 배포시간이 기하급수적으로 늘어나게 된다.
- 서비스를 부분적으로 scale-out하기가 힘들다.
- 부분의 장애가 전체 서비스의 장애로 이어지는 경우가 발생하게된다.


<br>

<img src="https://user-images.githubusercontent.com/45676906/95574135-740f4880-0a67-11eb-92de-d59fc1326cb7.png">

<br> <br>

## MSA의 장점

MSA는 서비스가 커지면서 생겼던 `Monolithic Architecture`의 문제점들을 어느정도 보완해 줄 수 있다.

- 배포(deployment) 관점
   - 서비스 별 개별 배포 가능 ( 배포 시 전체 서비스의 중단이 없음)

- 요구사항을 신속하게 반영하여 빠르게 배포할 수 있음.
    - 확장(scaling) 관점
    - 특정 서비스에 대한 확장성이 용이함.

- 클라우드 사용에 적합한 아키텍쳐.
    - 장애(failure) 관점
    - 장애가 전체 서비스로 확장될 가능성이 적음

- 부분적 장애에 대한 격리가 수월함
- 이외에도, 신기술의 적용이 유연하고, 서비스를 polyglot하게 개발/운영 할 수 있다는 장점이 있습니다.



<br>

## MSA 단점

`Monolithic Architecture`은 단순한 아키텍쳐인데 비해 `MSA`는 보다 복잡한 아키텍쳐로, 전체 서비스가 커짐에 따라 그 복잡도가 기하급수적으로 늘어날 수 있다.

- `성능` - 서비스 간 호출 시 API를 사용하기 때문에, 통신 비용이나, Latency가 그만큼 늘어나게 된다.
- `테스트` / 트랜잭션 - 서비스가 분리되어 있기 때문에 테스트와 트랜잭션의 복잡도가 증가하고, 많은 자원을 필요로 한다.
- `데이터 관리` - 데이터가 여러 서비스에 걸쳐 분산되기 때문에 한번에 조회하기 어렵고, 데이터의 정합성 또한 관리하기 어렵다.



<br>

# Reference

[https://velog.io/@tedigom/MSA-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-1-MSA%EC%9D%98-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-3sk28yrv0e](https://velog.io/@tedigom/MSA-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-1-MSA%EC%9D%98-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-3sk28yrv0e)