# 타입스크립트 고급 타입

## 타입스크립트 고급 타입

 타입스크립트의 타입 일관성을 더 효율적으로 지키기 위해서 타입스크립트에서 지원하는 고급 타입을 알아두면 좋습니다.   타입스크립트는 다음과 같은 고급 타입을 가지고 있습니다. 

* 유니언 타입 Union Types
* 문자열 리터럴 타입
* 룩업 타입
* non-nullabe 타입
* 네버 타입
* this 타입

### 유니언 타입 Union Types

 타입스크립트 1.4에 추가된 특징으로, **2개 이상의 타입을 하나의 타입으로 정의하는 타입**입니다. 다음과 같이 파이프\(\|\)를 이용해 선언합니다.

```typescript
let union : string | number | boolean;
```

 위와 같이 선언된 union 변수에는 string, number, boolean 자료가 모두 들어갈 수 있습니다. 유니언 타입은 함수의 매개변수를 타입별로 나눠 처리를 해야할 때\(함수 오버로딩\) 사용할 수 있습니다. 

```typescript
function overLoading(x: string | number | boolean) : string | number | boolean {
    if(typeof x === "string"){
        // x가 string 타입일 때 처리
        return x;
    }
    if(typeof x === "number"){
        // x가 number 타입일 때 처리
        return x;
    }
    if(typeof x === "boolean"){
        // x가 boolean 타입일 때 처리
        return x;
    }          
}
```

 만약 넣어야하는 타입이 클래스일 경우에는 typeof 대신 **instanceof**를 사용해 위와 같은 기능을 구현할 수 있습니다.  

#### 타입 가드 Type Guards

 유니언 타입은 여러타입을 받을 수 있다는 장점이 있지만 타입을 확신할 수 없다는 문제가 있습니다. 따라서 유니언 타입을  안전하게 사용하기 위해 타입 검사를 거쳐 다음과 같이 매개변수 값을 받아야 합니다.

```typescript
function typeGuards (x:number | boolean) : void {
    if(typeof x === "number"){
        // 타입 가드
    }
    if(typeof x === "boolean"){
        // 타입 가드
    }
}
```

 위와 같이 유니언 타입에 대한 타입 검사를 통해 타입 안정성을 주는 방법을 타입 가드\(Type Guards\)라고 합니다. 

### 문자열 리터럴 타입

 **문자열 리터럴 타입은 타입에 정의한 문자열만 할당받을 수 있게 하는 타입**입니다. 다음과 같이 사용할 수 있습니다.

```typescript
let stringLiteral:"Stark"|"Taeyun" = "Stark";
// stringLiteral은 "Stark"와 "Taeyun"이라는 값 외에 사용할 수 없습니다.
```

### 룩업 타입 Lookup Type

 룩업\(Lookup\)타입은 타입스크립트 2.1에 추가된 타입입니다. 주로 인덱스 접근 타입으로 불려집니다. 룩업 타입은 keyof를 통해 타입 T의 하위 타입을 생성해냅니다.

### non-nullabe 타입

### 네버 타입

### this 타

