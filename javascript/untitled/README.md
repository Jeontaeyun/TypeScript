# 자바스크립트의 객체

## 객체 \| Object

 객체 지향 언어\(OOP\)는 프로그래밍계에서 중요한 개념입니다. **현실의 사물을 프로그래밍에 반영한 하나의 단위**가 객체입니다.

```javascript
const stark = {
    name: "stark",
    age: 25,
    major: "electronic engineering",
    lived : "melbourn",
    hobby : ["programming","drawing","writing"]
}
```

 나라는 사람을 객체로 만들어 이름, 나이, 전공, 거주지, 취미로 만들면 위와 같은 객체가 됩니다.

### 객체의 속성 \| Property

 객체 안을 보면 **key : value**의 패턴이 반복되는 것을 확인할 수 있습니다. 위의 객체를 보면 name: "stark" , age: 25 등 등이 하나의 **속성\(Property\)**입니다.

 객체의 속성은 **키: 값**의 관계로 이루어져있습니다. 이때 키를 **속성명**이라고도 합니다. 또한,  속성명은 따옴표가 없어도 괜찮습니다.

### 객체의 메소드 \| Method

```javascript
const stark = {
    hi() {
        (...)
}
```

 위와 같이 객체안에 들어있는 함수를 **메소드**라고 합니다. 과거에는 `hi : function(){}`과 같이 메소드를 지정해주었는데 ES+ 이후 부터는 객체 리터럴이 더 간결하게 변해 위와같이 메소드를 설정할 수 있습니다.

### 객체의 속성 접근

```javascript
stark.name;            // 속성 호출 
starkt['name'];        // 속성 호출 []방식
stark.hi();            // 메소드 호출
```

### 객체의 속성 제거 \| delete 키워드

```javascript
delete stark.name;      // 객체의 name 속성 제
```

## 배열 \| Array

 배열은 \[\]로 감싸져 요소\(item\)들을 보관하는 자료형입니다. 

 자바스크립트의 배열은 다른 언어의 배열과는 다르게 배열의 길이를 미리 지정해줄 필요가 없고 자동적으로 늘어나거나 줄어듭니다.

```javascript
const arrayTest = [1, "stark", [3,2,1], {hello: 3}];
```

 배열은 키가 없다는 점에서 객체와 차이가 있습니다. 하지만 배열에는 객체에는 없는 추가적인 기능이 있기에 배열에 대해서 잘 파악해두는 것이 중요합니다.

