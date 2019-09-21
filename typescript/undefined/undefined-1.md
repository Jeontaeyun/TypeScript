# 타입스크립트 제네릭 함수

## 제너릭 함수 Generic Function

 **타입 매개변수**는 제네릭에서 가장 중요한 요소입니다. 이는 **함수 선언에 함수를 제너릭 함수\(Generic Function\)로 변경**할 수 있게 합니다. 

```typescript
function genericFunction<T>(value1: T, vlaue2: T){
    return value1 + value2;
}

genericFunction<number>(1,2); //3
```

 만약 제너릭 함수의 매개변수 타입과 일치하지 않는 매개변수가 들어갈 경우 다음과 같은 에러가 발생합니다.

```text
Argument of type "..." is not assignable to parameter of type "..."
```

### 제너릭 함수 T+T 연산 

**제너릭 함수에서 중요한 것은 T+T연산이 되지 않는다는 것**입니다. 타입 매개 변수 T로 지정된 변수 간에는 연산을 할 수 없으므로 불필요한 캐스팅 코드를 추가해야 합니다. 

```typescript
return String(value1) + String(value2);
```

### 오버로드 함수를 이용한 타입 매개변수 간의 연산

 **오버로드 함수\(Overload Function\)을 이용해 T+T와 같은 타입 매개변수 간의 연산이 가능**합니다. 

```typescript
function overGeneric<T>(value1: T, value2: T) : T;
function overGeneric(value1: any, value2: any){
    return value1 + value2;
}
```

 T+T연산이 되지 않는 문제를 해결하기 위해 본 함수 위에 오버 로드 함수를 추가하면 가능합니다. 

### 타입 매개변수 제한 \| extends

 타입 매개변수의 T는 어떤 타입이든 받아들이기 때문에 타입을 몇 가지로 제한할 때가 있습니다. 이를 위해 **extends 키워드**를 사용할 수 있습니다. 

```typescript
<T extends number>
```

 위와 같이 extends 키워드로 타입 매개변수를 number타입으로 묶었습니다\(Bound\). 해당 타입 매개변수 T를 **바운드 타입 매개변수\(Bounded Type Parameter\)**라고 합니다.

### 유니언 타입과 제너릭 함수

 타입 매개변수 T에 유니언 타입을 상속해 선언하여 제너릭의 유연성을 잃지 않으면서 타입을 적당히 제약할 수 있습니다. 

```typescript
<T extends string | number | boolean>
```

### 제너릭 함수 타입 매개변수 2개 이상 선언

 제너릭 함수에 타입 매개 변수를 여러 개 사용하기 위해서는 다음과 같이 타입 매개 변수를 지정해주면 됩니다. 

```typescript
let arr : Array<any> = [];
function doubleGeneric<T,K> (value1: T , value2: K): T;
function doubleGeneric (value1: any, value2: any){
    arr[value1] = value2;
}
doubleGeneric<number, string> (1, "Stark");
```

