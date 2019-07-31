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

### 객체의 얇은 복사 \| Shallow Copy

```javascript
const array = [{name: 'stark'},{name: 'hailey'},{name: 'stacey'}];
// Array.prototype.slice.call();로 객체 복사
const shallow = Array.prototype.slice.call(array);
shallow[0].name = 'Taeyun';
shallow[1] = {name: 'Taeyun'};
console.log(array);
// [{name: 'Taeyun'},{name: 'hailey'},{name: 'stacey'}]
```

 이때 call함수는 함수의 기본 메소드로 call\(this, para\_1, para\_2, ...\)와 같이 사용해서 함수를 실행하는 메소드입니다. 즉, 이렇게 되면 Array 객체의 prototype인 slice에 array를 this로 넣어서 생성하라는 뜻이 됩니다.

 이렇게 되면 앞서 발생한 메모리를 공유하는 문제를 해결하고 array 변수와 shallow 두 개의 메모리 상태로 객체를 사용할 수 있습니다.

 이 말은 하나의 객체의 값을 바꿔도 다른 값에 서로 영향을 미치지 않는다는 것을 뜻합니다.

### 객체의 깊은 복사 \| Deep Copy

 위와 같은 방법으로 복사를 하면, 상위 객체인 shallow\[1\]의 값은 변하지 않았지만, shallow\[0\].name의 값은 바뀐 것을 알 수 있습니다. 

 이는 위의 복사 방법으로는 상위 객체는 새로 생성되지만 내부 객체는 참조하기 때문입니다.

 만약, 내부의 객체 까지 모두 새로 생성되도록 객체를 깊게 복사\(Deep Copy\)하기 위해선 다음과 같이 만들어 주면 됩니다.

```javascript
fucntion copyObj(obj){
    // 빈 객체를 생성합니다.
    let copy = {};
    // 복사할 값이 Array이면
    if(Array.isArray(obj)){
        // copy에 배열을 잘라 다시 넣어줍니다.
        copy = obj.slice().map((v) => {
            return copyObj(v);
        });
    // obj이 객체이면
    } else if (typeof obj === 'object' && obj !== null){
        // 객체안의 속성명을 반복해서
        for(var attr in obj){
            if(obj.hasOwnProperty(attr)){
                // copy객체에 속성명:obj의 속성명을 같은 기능을 반복해서 넣어 줍니다.
                copy[attr] = copyObj(obj[attr]);
            }
        }
    } else {
        copy = obj;
    }
    return copy;
}

const obj = {a:1, b:2, c:[{d:null, e:'f'}]};
const obj2 = copyObj(obj);
```

 위의 copyObj\(obj\)함수는 Deep Copy를 위해서 만들어준 함수 입니다. 이 원리를 이해함으로서 Deep Copy를 위한 함수를 자체 제작 할 수 있습니다.

| 구분  | 설명  |
| :--- | :--- |
| for\( var attr in obj\){...} | 객체안의 키\(Key,속성명\)을 attr로 받아서 반복 동작합니다. 키가 숫자면 순서대로 반복되지 않습니다. 따라서 숫자인 키가 없을 때 사용하는 것이 좋습니다 |
| obj.hasOwnProperty\(keyName\) | 메소드로 상속되지 않은 자기의 속성인지를 판단하는 메소드입니다 |

### 함수의 복사 \| Bind

 함수를 복사하고 싶을 때는 bind 메소드를 이용하면 됩니다.

```javascript
const func_target = function(){
    alert('hi');
};
func_copy = func_target.bind(this);
func2();    //'hi'
```



