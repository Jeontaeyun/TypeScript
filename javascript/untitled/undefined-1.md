# 객체의 얇은 복사와 깊은 복사

## Shallow Copy and Deep Copy

### 객체의 복사 

 자바스크립트는 문자열, 숫자, 불린을 제외한 객체를 변수에 대입해서 복사하면 값을 복사하는게 아니라 **메모리 주소\(참조 \| Reference\)를 복사해 변수에 대입해줍니다.** 

 따라서 자바스크립트의 객체를 생성한 후 다른 변수에 복사해주어도 그 값이 독립적으로 동작하지 않고 서로 영향을 미칩니다.

```javascript
const objectTest = {
    data_1 : "hi",
    data_2 : 1,
    data_3 : [1,2,3]
}

const objectCopy = objectTest;
objectCopy.data_3 = "Immer";
console.log(objectTest);

// {
//    data_1: "hi",
//    data_2: 1,
//    data_3: "Immer"
// }
```

 즉, 위와 같이 복사된 객체의 값을 변경했지만 기존의 objectTest의 값 또한 바뀌게 됩니다.

### Shallow Copy\(얇은 복사\) 와 Deep Copy\(깊은 복사\) 

| 구분  | 설명  |
| :--- | :--- |
| Shallow Copy | 가장 상위 객체만 새로 생성되고 내부 객체들은 참조 관계인 객체 복사 |
| Deep Copy | 가장 상위 객체부터 내부 객체들 까지 모두 새로 생성되는 객체 복사  |

