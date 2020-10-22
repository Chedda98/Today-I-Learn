# 인증(Authentication) VS 인가(Authorization)

<br>

### `인증(Authentication)`

어떤 A라는 건물에 출입을 할 때, 출입증이 있다면 들어갈 수 있고 없다면 들어갈 수 없다. 이렇게 `식별가능한 정보로` 서비스에 등록된 유저의 신원을 입증하는 과정을 `인증`이라 한다.


### `인가(Authorization)`

하지만 `출입증`으로 회사의 모든 곳을 다 돌아다닐 수 있는 것은 아니다. 만약 A라는 10층짜리 건물에 내가 다니는 회사는 5층이라면 나머지 층에는 출입을 할 수 있다.
이러한 것을 `인가`라고 한다. 한마디로 `권한에 대한 허가`를 나타내고, `인증된 사용자에 대한 자원 접근 권한 확인`이다.

<br>

```
또 다른 예로는 어떤 게시글을 내가 작성하였을 때, 다른 사람들은 이 글에 대해 수정, 삭제 권한이 없다. 
이것이 인가가 적용이 된 예시이다.
```

`따라서 반드시 인증이 인가보다 선행되어야 하는 개념이다`
