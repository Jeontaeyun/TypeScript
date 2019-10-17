# 타입스크립트의 내장 타입

## 타입스크립트 내장 타입

 타입스크립트에서만 지원되는 내장 타입\(Basic Type\)도 존재한다.

### any 타입

 any타입은 제약이 없는 타입으로 어떤 타입의 값도 받아들일 수 있는 타입입니다. **any타입은 외부 라이브러리의 연산 결과를 받는 것 같이 타입 결과를 예측할 수 없을 때 유연한 대처가 가능**합니다. 

 any타입은 타입스크립트의 모든 타입의 가장 최상위 타입입니다. 즉, 모든 타입은 any타입의 하위 타입입니다.

#### 01. any타입과 object타입

 object타입은 any 타입처럼 타입 구분 없이 값을 할당할 수 있는 특성이 있습니다. 그러나 속성의 유무를 검사하는 시점이 다릅니다.

 any타입으로 선언한 변수는 속성의 유무를 런타임 시에 검사하지만, object타입으로 선언한 변수는 컴파일 시간에 속성의 유무를 검사합니다.

#### 02 .noImplicitAny 옵션 

 tsconfig.json의 "noImplicitAny"타입을 true로 설정하면 자동적으로 타입을 지정해 주지 않으면 any타입을 지정해주는 것을 막고 모든 변수에 타입을 지정해야 합니다. 

또한, any를 명시적으로 표시해주어야 합니다. 

### 배열 타입과 제너릭 배열 타입

 배열은 여러 개의 값을 하나의 변수에 담아 관리하는 자료구조로 타입 스크립트에서는 두 가지 형태의 배열이 있습니다. 

* 배열 타입 \( Array Type \)
* 제네릭 배열 타입 \( Generic Array Type \)

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>&#xBC30;&#xC5F4; &#xD0C0;&#xC785;</b>
      </td>
      <td style="text-align:left">
        <p>let commonArray : number[ ] = [ 1, 2, 3, 4, 5]; &#xC640; &#xAC19;&#xC774;
          &#xC9C0;&#xC815;&#xD574;&#xC8FC;&#xB294; &#xBC30;&#xC5F4;</p>
        <p>&#xB2E4;&#xC591;&#xD55C; &#xD0C0;&#xC785;&#xC744; &#xB123;&#xC5B4;&#xC8FC;&#xACE0;
          &#xC2F6;&#xC73C;&#xBA74; &#xC720;&#xB2C8;&#xC5B8; &#xD0C0;&#xC785;&#xC744;
          &#xC774;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;</p>
        <p>let commonArray : (number | string | boolean)[ ] = [1, &quot;hello&quot;,
          false];</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xC81C;&#xB108;&#xB9AD; &#xBC30;&#xC5F4; &#xD0C0;&#xC785; </b>
      </td>
      <td style="text-align:left">
        <p>let genericArray : Array&lt;number&gt; &#xC640; &#xAC19;&#xC774; &#xD0C0;&#xC785;&#xC744;
          &#xC9C0;&#xC815;&#xD558;&#xB294; &#xBC30;&#xC5F4;</p>
        <p>Array&lt;T&gt;&#xC640; &#xAC19;&#xC774; &#xC120;&#xC5B8;&#xD558;&#xBA70;
          T&#xC5D0; &#xD0C0;&#xC785;&#xC774; &#xB4E4;&#xC5B4;&#xAC11;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>### 튜플 타입 

 **튜플\(Tuple\)은 n개의 요소로 이뤄진 배열에 대응 하는 타입**을 의미합니다. 튜플 타입은 배열 요소에 대응하는 n개에 대한 타입입니다 .   
  
 즉, 튜플은 지정한 타입과 타입의 수 만큼만 값을 할당 받을 수 있고, 다른 타입을 할당하거나 그 수가 초과되면 에러를 발생시키는 타입입니다.

```typescript
let tuple : [string, number] = ["Stark", 27]
// 배열에 더 많은 값을 할당하면 에러가 발생합니다. 
```

### 

### Enum 타입

 JavaScript를 쓰면서 느끼는 아쉬운 점 중 하나인 **Enum\(Enumeration \| 엵거형\)**을 타입스크립트에서는 도입했다. **유한하면서도 여러 가지 상태를 가질 수 있는 변수를 선언**할 때 유용하다. 

```typescript
enum Color {
    RED,
    GREEN,
    BLUE
}
```

로 선언을 한 뒤 다음과 같이 사용할 수 있다.

```typescript
setColor(color : Color){
    // feature
}
setColor(Color.RED);
```

 Enum은 하나의 타입이기도 하지만, JavaScript 런타임에서도 사용되는 하나의 변수로 볼 수도 있다. 

 **JavaScript 런타임에서도 사용된다는 말은, 클래스처럼 컴파일 결과물이 존재한다는 것**이다. 예를 들어, 위에서 선언한 Color 타입은 아래와 같이 컴파일 된다. 

```javascript
var Color;
(function (Color){
    Color[Color["RED"] = 0] = "RED";
    Color[Color["GREEN"] = 0] = "GREEN";
    Color[Color["BLUE"] = 0] = "BLUE";
})(Color || (Color = {} ));
```

 결과적으로 위의 코드는 다음과 같이 된다. 

```javascript
var Color = {
    RED: 0,
    GREEN: 1,
    BLUE : 2,
    0: "RED",
    1: "GREEN",
    2: "BLUE"
}
```

 **enum 키워드**는 기본적으로 **리버스 매핑\(Reverse Mapping\)을 지원**한다. 리버스 매핑이란 키로 값을 얻을 수 있을 뿐만 아니라, 값으로도 키를 얻을 수 있는 방식을 말한다. 

 enum을 사용할 때 대개의 우 숫자 값은 의미가 없으므로, DB에 값을 삽입할 때를 위해서 의미가 있는 **문자열 값으로 초기화하고 싶은 경우가** 있다.

 그럴 경우 다음과 같이 사용하면 된다. 

```typescript
enum Color {
    RED = 'red',
    GREEN = 'green',
    BLUE = 'blue'
}
```

 enum은 기본적으로 **읽기 전용\(Read-only\)**이다. 

### void, null, undefined 특수 타입

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>void</b>
      </td>
      <td style="text-align:left">
        <p>&#xD568;&#xC218;&#xC758; &#xBC18;&#xD658;&#xAC12;&#xC774; &#xC5C6;&#xC744;
          &#xB54C; &#xC9C0;&#xC815;&#xD558;&#xB294; &#xD0C0;&#xC785;</p>
        <p>&#xD574;&#xB2F9; &#xD0C0;&#xC785;&#xC5D0;&#xB294; <b>null&#xC774;&#xB098; undefined&#xB9CC; &#xD560;&#xB2F9;&#xD560;</b> &#xC218;
          &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>null</b>
      </td>
      <td style="text-align:left">typeof&#xB85C; &#xD638;&#xCD9C;&#xD558;&#xBA74; object&#xB294; &#xB098;&#xC624;&#xC9C0;&#xB9CC;
        &#xBE48; &#xAC1D;&#xCCB4;&#xB97C; &#xC758;&#xBBF8;&#xD55C;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>undefined</b>
      </td>
      <td style="text-align:left">&#xBCC0;&#xC218;&#xAC00; &#xC120;&#xC5B8;&#xB418;&#xC5C8;&#xC9C0;&#xB9CC;
        &#xC544;&#xC9C1; &#xC544;&#xBB34; &#xAC12;&#xB3C4; &#xD560;&#xB2F9;&#xB418;&#xC9C0;
        &#xC54A;&#xC74C;&#xC744; &#xC758;&#xBBF8;&#xD55C;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>{% hint style="info" %}
**strictNullChecks 옵션**

 tsconfig.json의 "strictNullChecks"옵션을 true로 하면 변수에 할당되던 null, undefined가 더 이상 할당되지 못하고 컴파일 오류를 발생시킵니다.   
  
타입스크립트에서는 변수를 선언할 때 값을 할당하지 않았음을 나타내기 위해 선언한 변수에 null을 할당하는 것을 권장하지 않습니다. 
{% endhint %}

{% hint style="info" %}
**null과 undefined 비교**

* undefined === undefined        -&gt;   true
* undefined == undefined          -&gt;   true
* null === undefined                   -&gt;   false
* null == undefined                     -&gt;   true 
{% endhint %}



