# 반복문

## 반복문

 반복문은 프로그래밍에서 반복되는 작업을 할 때 자주 사용하는 프로그래밍 제어문입니다. 예를 들어 하나의 컴포넌트를 반복해서 렌더링 해준다거나, 자료구조를 구현할 때   반복문을 통해서 현재의 위치를 찾는다거나 반복문을 사용할 일은 정말 다양합니다.

 대표적인 반복문은 for문과 while문이 있습니다. 또 배열을 반복하는 map 메소드와 for-each문과 객체를 반복하는 for-in문, for-of문도 있습니다. 각각 한번 알아봅시다.

### For문

 대표적인 반복문으로 다양한 프로그래밍 언어에서 채택하고 있는 반복문 구문입니다.

```javascript
for(시작변수 ; 조건 ; 끝){
    (반복 작업 할 내용...)
}
```

### While문

 for문과 마찬가지로 대표적으로 사용하는 반복문 구문입니다. 조건이 참이 되는 동안은 while문 안의 작업이 반복됩니다.

```text
while(조건){
    (반복 작업 할 내용...)
}
```

 반복문을 할 때 주의해야할 사항은 절대로 무한 반복의  루프에 빠지게 하지 않는다는 것입니다. 왜냐하면 반복문이 계속 실행된다면 프로그램이 메모리 부족현상으로 종료될 수 있기 때문입니다.

| 구분 | 설명 |
| :--- | :--- |
| break; | while문 안에 넣어서 사용하면 반복문을 중단할 수 있습니다. |
| continue; | while문 안에 넣어서 사용하면 반복문을 하는 중 continue아래 작업은 수행하지 않고 다음 반복으로 넘어갑니다.  |

### Map메소드

  map은 배열의 요소를 일괄적으로 변경하는데 효과적인 메소드입니다. map의 목적은 콜백함수의 리턴을 모아서 새로운 배열을 만드는 것이 목적입니다.

```javascript
const arr = ['foo','hello','mel'];
const arr2 = arr.map((item)=>{
    return item.length;
});
```

### For-Each문

 forEach 구문은 배열을 반복하는 방법으로 다음과 같은 코드를 forEach를 이용해서 수정할 수 있다.

\[Before\]

```javascript
const arr = [3,9,4];
for(let i = 0; i <arr.length; i++){
    if(arr[i] % 2 == 0){
        console.log(arr[i]);
    }
}
```

\[After\]

```javascript
const arr = [3,9,4];
arr.forEach((n) => {
    if(n%2 == 0){
        console.log(n);
    }
});
```

### For-in문

 for-in문은 객체안의 속성을 반복하기 위해서 사용되는 반복 메소드입니다. 즉, 객체 안의 키의 값들을 반복하는 메소드입니다. for-in 구문은 다음과 같이 사용할 수 있습니다.

```javascript
const testObject = {hello: "hi", name : "Taeyun", age : 25};
for (let i in testObject){
   alert(i);   
}
// hello, name, age
```

### For-of문 \(ES+\)

 ES+ 부터는 객체의 컬렉션의 요소를 반복하는 for-of문이 생겼습니다. 즉, 객체안의 속성값을 반복합니다.

```javascript
const testObject = {hello: "hi", name : "Taeyun", age : 25};
for (let i of testObject){
   alert(i);   
}
// hi, Taeyun, 25
```

 단, for-of가 반복하는 컬렉션은 \[Symbol.iterator\]라는 속성이 있어야하는데 이런 컬렉션에는 Array, String, TypedArray, Map, Set, DOM, 생성기\(Generator\)등이 있습니다.

