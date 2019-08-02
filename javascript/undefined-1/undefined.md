# 조건문

## 조건문 \| Condition

 프로그래밍에서 중요한 제어문 중 하나는 조건문입니다. 조건문은 특정한 조건 아래에서 동작을 분기\(구분\)하는 제어문입니다. 자바스크립트의 대표적인 조건문에는 if와 while이 있습니다.

### If 문

 if문은 대부분의 프로그래밍 언어에 존재하는 대표적인 조건문입니다. 다음과 같이 사용합니다.

```javascript
if(조건) {
    (조건에 따라 실행되야 할 구문)
}else if(조건)
    위의 조건을 만족하지 않고 다음 조건에 따라 실행되야 할 구문
}else{

}
```

 이때 **0, -0, null, false, NaN, undefined, ' ' 등은 false로 처리됩니다**. 단, **\[\]는 조건 안에서 true로 처리**됩니다.

### 삼항 연산자

 if-else문은 삼항 연산자를 통해서 쉽게 구현할 수 있습니다. 이를 통해 조금더 간결한 코드 작성이 가능합니다.

```javascript
const i = 10;
const j;
if(i > 10){
    j=15;
}
else{
    j=5;
}
```

 위와 같은 코드를 다음과 같이 바꿀 수 있습니다.

```javascript
const j = (i >10) 15 : 5;
```

### Switch 문

 자바스크립트에서는 조건문으로 switch-case문을 지원합니다. 이는 if-else if -else패턴을 가독성 높은 코드로 작성할 수 있도록 해줍니다.

```javascript
switch(c){
    case "hi":
        alert("hi");
        break;
    case "hello":
        alert("hello");
        break;
    (...)
    default:
        alert("etc");
}
```

 Switch문은 받은 인자가 case의 조건과 같으면 해당 동작을 실행시켜주는 문법입니다. 

 주의할 점은 case하나에 break를 지정해 조건문에서 탈출하도록 해주어야합니다. 그렇지 않으면 해당 조건 아래의 코드를 모두 동작시킵니다. 

#### 폴스루 \| Fall-Through

 case 절에서 break문을 사용해 switch 문을 벗어나는데 경우에 따라 break문을 생략할 수 있습니다. break문을 생략하면 다음 case절들이 break을 만날 때 까지 실행됩니다.

 위와 같은 상황을 떨어지다라는 의미의 fall through라고 부릅니다. 폴 스루는 보통 두가지 이유로 발생합니다.

* 개발자가 같은 로직을 가지는 case 문을 사용하기 위해 fall-through를 발생시킵니다.
* 개발자가 실수로 break문을 지정하지 않아 폴스루를 발생시킵니다. 

{% hint style="info" %}
앞으로 사용하게 될 TypeScript에서는 개발자의 Fall-Thorugh를 막아주는 컴파일 설정이 있습니다. tsconfig.json에서 다음과 같이 설정하면 됩니다.
{% endhint %}

```javascript
{
    "compilerOptions" : {
        "noFallthroughCasesInSwitch" :true
    }
}
```

 만약 tsc 명령어를 이용해 파일 단위로 컴파일할 때 폴스루를 방지하려면 --noFallthroughCasesInSwitch 옵션을 추가할 수 있습니다.

