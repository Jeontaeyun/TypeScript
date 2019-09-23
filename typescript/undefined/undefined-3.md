# 타입스크립트 제너릭 활용

## 타입스크립트 제너릭 활용

### 룩업 타입을 제너릭 클래스에 적용

 룩업\(Lookup\) 타입은 keyof로 속성을 포함하는 대상을 탐색해 유니언 타입처럼 동작합니다. 

```typescript
interface INumber {
    one: number;
    two: number;
    three: number;
}
type NumberKeys = keyof INumber;     -> "one" | "two" | "three"
```

 이를 이용해 다음과 같이 구현할 수 있습니다.

```typescript
function getValue<T, K extends keyof T>(obj: T, key:K){
    return obj[key];
}
let obj = {name: "stark", age: 25, job: "developer"};
console.log(getValue(obj, "job"));
// getValue의 T가 obj로 정해져서 key 매개변수에는 "name" , "age" , "job"외에
// 넣어줄 수 없다(룩업 타입)
```

 타입 매개변수 K는 타입 매개변수 T에 의해 정해지는 룩업 타입입니다. 따라서 타입 매개변수 K는 keyof를 이용해 타입 매개변수 T의 속성을 탐색해 하나의 속성만 허용하도록 제약합니다. 

### 인터페이스를 상속해 제너릭 확장

 인터페이스는 클래스가 구현해야 할 메서드나 프로퍼티를 선언할 수 있습니다. 만약에 구현해야 할 클래스가 제너릭 클래스라면 인터페이스는 **제너릭 인터페이스\(Generic Interface\)로 선언**해야 합니다.

```typescript
interface GenericInterface<T> {
    ...
}
```

 이와 관련된 예시는 다음과 같습니다.

```typescript
interface GenericInterface<T>{
    unique(array: Array<T>): Array<T>;
}
class GenericClass<T> implements GenericInterface<T>{
    unique(array: Array<T>) : Array<T>{
        ...
    }
}
```

### 맵 객체의 선언과 타입 지정 방법

 자바스크립트 맵 객체는 타입을 지정할 수 없어 타입 안정성이 없었습니다. 반면 **타입스크립트에서는 맵 객체에 타입을 지정할 수 있어 타입 안정성**이 있습니다.

| 메서드 | 설 |
| :--- | :--- |
| Map.prototype.clear\(\) | 맵 객체에 추가된 모든 요소를 삭제 |
| Map.prototype.set\(키,값\) | 맵 객체에 키와 값을 추가 |
| Map.prototype.delete\(키\) | 맵에서 키에 해당하는 특정 요소를 삭제 |
| Map.prototype.entries\(\) | 새로운 이터레이터 객체를 반환 |
| Map.prototype.forEach\(\) | 각 순회마다 키-값 쌍에 대한 처리를 지원 |
| Map.prototype.get\(키\) | 키가 있는지 확인하고 있으면 값을 반환  |
| Map.prototype.has\(키\) | 키가 있는지 확인하고 있으면 true를 반 |
| Map.prototype.keys\(\) | Iterator 객체를 생성해 반환 |
| Map.prototype.values\(\) | 배열 이터레이터를 반환 |

맵 객체에 타입을 지정하기 위해서는 다음과 같이 사용합니다.

```typescript
let list: Map<number, string> = new Map<number,string>();
```

맵 객체를 할당받을 변수에 맵 객체의 타입이 선언돼 있다면 타입 안정성이 보장되므로 맵 객체를 생성할 때 타입 인수를 생략해도 됩니다.

```text
let list: Map<number, string> = new Map();
```

{% hint style="info" %}
**제너릭 기반의 자료구조**

스택\(Stack\), 큐\(Queue\), ArrayList 등과 같은 자료구조를 만들어 사용하기 위해 제너릭을 이용하여 범용적으로 사용 가능한 자료구조를 만들 수 있습니다.
{% endhint %}

