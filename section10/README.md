# 다형성

## 다형성 Polymorphism

- Poly- 다양한
- morph 변하다
- 어떤 개체가 다양한 형태로 변할 수 있는 능력

### 다형성

- 같은 지시를 내렸는데 다른 종류의 개체가 동작을 달리하는 것
- 어떤 함수 구현이 실행될지는 실행 중에 결정됨 (늦은 바인딩 late binding)
- 일반적인 함수 호출은 이른 바인딩 (early binding)
    - 컴파일 중에 결정됨
- 다형성 혜택을 받으려면 상속 관계가 필요
    - 부모 개체에서 함수 시그내처 선언
    - 자식 개체에서 그 함수를 다르게 구현(오버라이딩)
- 실용적인 용도
    - 다른 종류의 개체를 편하게 저장 및 처리 가능
- 서브타입 다형성 (99.9 %)

```java
public class Animal {
    public void shout() {
        System.out.println("동물");
    }
}

public class Bird extends Animal {
    public void shout() {
        System.out.println("짹짹");
    }
}

public class Cat extends Animal {
    public void shout() {
        System.out.println("야옹");
    }
}

public class Dog extends Animal {
    public void shout() {
        System.out.println("멍멍");
    }
}
```

#### 상속은 다형성에 필요한 선수 조건

#### 부모 클래스에서 메서드의 시그내처를 정해줘야 한다

#### 그렇지 않으면 부모 클래스형 변수에서 호출 불가

### 오버라이딩은 선택사항

- 상속을 통해 부모 클래스에서 구현한 메서드를 물려 받음
- 이 메서드에 아무 일도 안 하면 부모 동작을 그대로 사용
- 자식 클래스가 원하는 경우 구현을 바꿈
    - 메서드 시그내처는 유지
- 부모 동작 중에 필요한 것만 고처 사용 가능

#### 부모 동작도 유지하면서 오버라이딩 가능

### 다형성의 장점

- 각 자료형 코드가 클래스 안에 들어가서 *캡슐화*
- 유지 보수성 높아짐
- 새로운 클래스를 추가할 때 클래스 코드만 추가하면 된다
- 클라이언트가 작성할 코드가 줄어든다

### 다형성은 늦은 바인딩

- 실제로 호출되는 메서드 구현이 프로그램 실행 중에 결정된다는 의미
- 동적 바인딩이라고도 한다
- 이른 바인딩
    - 정적 바인딩
    - C언어 함수 호출 방식
    - 어떤 함수 구현을 호출할지 빌드시 결정됨
    - C에서 다형성을 지원 안하기 때문

### C 함수 포인터와의 비교

- 함수포인터는 늦은 바인딩

### 자바와 C의 기본 함수 호출 방식 비교

- C: 이른 바인딩, 함수 포인터로 늦은 바인딩도 가능
- 자바: 늦은 바인딩, 가상 메서드라고 함

- 가상 메서드
    - 자식 클래스에서 동작을 오버라이딩 할 수 있는 메서드
    - 다형적인 메서드

### 이른 바인딩 vs 늦은 바인딩 : 성능

- 이른 바인딩
    - 컴파일러가 실제로 어떤 함수를 호출해야 하는지 앎
    - 컴파일 중에 충분한 시간을 들여 최적화 가능
    - 실행 중에는 충분한 시간이 없음

