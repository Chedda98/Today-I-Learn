## 다형성 (polymorphism) 이란?

### 다형성

객체지향에서 다형성이란 `여러 가지 형태를 가질 수 있는 능력`을 의미한다. 구체적으로 말하자면 `조상클래스 타입의 참조변수로 자손클래스의
인스턴스를 참조할 수 있도록` 하였다. 

<br>

```
Tv t = new Tv();
CaptionTv c = new CaptionTv(); 
```

원래는 위와 같이 인스턴스의 타입과 일치하는 타입의 참조변수만을 사용했다. 그런데 만약 `TV`와 `Captain`이 서로 상속관계에 있다면 
다음과 같이 조상 클래스 타입의 참조변수로 자손 클래스의 인스턴스를 참조할 수 있다.

<br>

```
Tv t = new Captain();
```

위의 경우 실제 인스턴스가 `Captain()`타입이라 할지라도, 참조변수 t로는 `Captain()`의 모든 필드를 참조할 수 없다.
TV타입의 참조변수 t로는 `Captain()`클래스가 `Tv`클래스로부터 상속받은 필드만 사용할 수 있다. 

<br>

```
Captain t = new Tv();
```
하지만 위와 같이 `자손타입의 참조변수로 조상타입의 인스턴스를 참조하는 것을 불가능하다`

<br>

### 참조변수의 형변환

서로 `상속관계`에 있는 클래스사이에만 형변환이 가능하다. 

```
자손타입 -> 조상타입(Up-casting) : 형변환 생략가능
조상타입 -> 자손타입(Down-casting) : 형변환 생략불가
```

형변환은 참조변수의 타입을 변환하는 것이지 인스턴스를 변환하는 것은 아니기 때문에 참조변수의 형변환은 인스턴스에 아무런 영향을
미치지 않는다. 단지 참조변수의 형변환을 통해서, 참조하고 있는 인스턴스에서 사용할 수 있는 멤버의 범위(개수)를 조절하는 것뿐이다.

<br>

```java
public class Test {
    public static void main(String[] args) {
        Car car = new Car();
        Car car2 = null;
        FireEngine fe = null;
        
        fe = (FireEngine)car;
    }
}

class Car { }

class FireEngine extends Car { }
```

위의 예제는 컴파일은 성공하지만, 실행 시 `에러(ClassCastException`가 발생한다. 에러가 발생한 곳은 `fe = (FireEngine)car`이다.
캐스트 연산자를 이용해서 조상타입의 참조변수를 자손타입의 참조변수로 형변환한 것이기 때문에 문자가 없어 보이지만, `문제는 참조변수 car가 참조하고 있는 인스턴스가 Car타입의 인스턴스라는데 있다`

<br>

```
한마디로 정리하자면 car 참조변수는 Car 클래스의 인스턴스를 가리키고 있다. 그런데 갑자기 (FireEngine)으로 형변환을 하라면 할 수가 없다.
만약에 car 참조변수가 업캐스팅이 되어 FireEngine을 가르키고 있다면 이 때는 FireEngine의 인스턴스 자체를 가리키고 있고 업캐스팅에 의해서 참조할 수 있는 멤버의 개수만
제한이 된 것이기 때문에 다운캐스팅이 가능하다. (따라서 다운캐스팅이 가능한 상황 instanceof 연산자를 이용해서 파악하자)
```
