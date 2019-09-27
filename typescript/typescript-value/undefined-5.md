# 타입 선언과 변경

## 타입 에일리어스

### 타입 에일리어스

 타입 에일리어스\(Type Alias\)는 타입스크립트 1.4버전 부터 지원되는 특성으로 기존 타입에 새로운 이름을 만들어 주는 기능입니다. 

```typescript
type <바인딩 식별자(Binding Identifier)> = 타입;
```

 타입에 새로운 별칭을 만드는 과정을 **에일리어싱\(Aliasing\)**이라 합니다. 

### 타입 추론 \| Type Inference

 타입스크립트에서는 값을 할당할 때 타입을 명시하지 않으면 타입 추론\(Type Inference\)을 통해 타입이 결정됩니다. 

 즉, 변수의 경우 각 변수가 처음 값이 할당되는 시점에 타입이 정해지므로 초기화가 이뤄진 다음에는 다음 타입의 값을 할당할 수 없습니다. 

### 타입 캐스팅과 변환 Type Casting

 타입 캐스팅\(Type Casting\)은 명시적으로 선언한 캐스팅 코드에 의한 타입 변경을 의미합니다. 따라서 JS 인터프리터에 의해 타입이 바뀌는 동적 타입 변환과 구분됩니다.

 **타입 캐스팅은 + 연산자**를 통해 수행할 수 있습니다.

### 타입 어설션 Type Assertion

 타입 어설션\(Type Assertion\)을 이용하면 타입스크립트 컴파일러가 타입 어설션 정보를 이용해 컴파일을 수행합니다. 따라서 타입 어설션은 컴파일 과정까지만 유효하고 컴파일 후에는 사라집니다. 

 타입 어설션은 **&lt;&gt;\(Angle Bracket\)방식**과 **as 문법\(as syntax\)**를 이용한 두 가지 방법이 있습니다. 

```typescript
let assertion: number = <number>myNum;
let sesertion: number = myNum as number;
```

&lt;&gt;는 JSX문법과 유사해 충돌을 일으키기 때문에 as 문법을 사용하는 것이 좋습니다.  

