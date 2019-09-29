# 노드 내장 객체

## 노드 내장 객체 

 노드에서는 기본적이니 내장 객체와 내장 모듈을 제공합니다. 따라서 바로바로 사용할 수 있습니다. 

### global 객체

 브라우저의 window와 은 전역 객체입니다. 모든 파일에서 접근할 수 있습니다. 모듈을 호출하는 require함수는 원래 global.require을 의미하며 **global은 생략할 수 있습니다**.

{% hint style="info" %}
**global 객체의 남용**

 global 객체의 속성에 값을 대입하여 파일 간에 데이터를 공유할 수 있지만, 이를 남용하면 안됩니다. 프로그램의 규모가 커질수록 어떤 파일에서 global 객체에 값을 대입했는지 찾기 힘들어 유지 보수에 어려움을 겪기 때문입니다.  
 다른 파일의 값을 사용하고 싶다면 모듈 형식으로 만들어서 명시적으로 값을 불러와 사용하는 것이 좋습니다.
{% endhint %}

### console 

 콘솔 객체는 주로 디버깅을 위해 사용됩니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>console.time(&#xB808;&#xC774;&#xBE14;)</p>
        <p>console.timeEnd(&#xB808;&#xC774;&#xBE14;)</p>
      </td>
      <td style="text-align:left">console.time(&#xB808;&#xC774;&#xBE14;)&#xACFC; console.timeEnd(&#xB808;&#xC774;&#xBE14;)
        &#xC0AC;&#xC774;&#xC758; &#xC2DC;&#xAC04;&#xC744; &#xCE21;&#xC815;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">console.log(&#xB0B4;&#xC6A9;)</td>
      <td style="text-align:left">&#xB85C;&#xADF8;&#xB97C; &#xC0AC;&#xC6A9;&#xD574; &#xCF58;&#xC194;&#xC5D0;
        &#xD45C;&#xC2DC;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">console.error(&#xC5D0;&#xB7EC; &#xB0B4;&#xC6A9;)</td>
      <td style="text-align:left">&#xC5D0;&#xB7EC;&#xB97C; &#xCF58;&#xC194;&#xC5D0; &#xD45C;&#xC2DC;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">console.dir(&#xAC1D;&#xCCB4;, &#xC635;&#xC158;)</td>
      <td style="text-align:left">&#xAC1D;&#xCCB4;&#xB97C; &#xCF58;&#xC194;&#xC5D0; &#xD45C;&#xC2DC;&#xD560;
        &#xB54C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.
        <br />&#xC635;&#xC158;&#xC758; colors&#xB97C; true&#xB85C; &#xD558;&#xBA74;
        &#xCF58;&#xC194;&#xC5D0; &#xC0C9;&#xC774; &#xCD94;&#xAC00;&#xB418;&#xC5B4;
        &#xBCF4;&#xAE30;&#xAC00; &#xD55C;&#xACB0; &#xD3B8;&#xD574;&#xC9D1;&#xB2C8;&#xB2E4;.
        <br
        />&#xC635;&#xC158;&#xC758; depth&#xB97C; &#xD1B5;&#xD574; &#xAC1D;&#xCCB4;
        &#xC548;&#xC758; &#xAC1D;&#xCCB4;&#xB97C; &#xBA87; &#xB2E8;&#xACC4;&#xAE4C;&#xC9C0;
        &#xBCF4;&#xC5EC;&#xC904;&#xC9C0;&#xB97C; &#xACB0;&#xC815;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">console.trace(&#xB808;&#xC774;&#xBE14;)</td>
      <td style="text-align:left">&#xC5D0;&#xB7EC;&#xAC01; &#xC5B4;&#xB514;&#xC5D0;&#xC11C; &#xBC1C;&#xC0DD;&#xD588;&#xB294;&#xC9C0;
        &#xCD94;&#xC801;&#xD560; &#xC218; &#xC788;&#xAC8C; &#xD574;&#xC90D;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>### setTimeout 과 setInterval

| 구분 | 설명  |
| :--- | :--- |
| setTimeout\(콜백함수, 리초\) | 주어진 밀리초 이후에 콜백 함수를 실행합니다.  |
| setInterval\(콜백함수, 밀리초\)  | 주어진 밀리초마다 콜백 함수를 반복 실행합니다.  |
| setImmediate\(콜백 함수\) | 콜백 함수를 즉시 실행합니다.  |

 해당 함수들은 모두 아이디를 반환하기에 아이디를 통해 타이머를 취소할 수 있습니다. 

| 구분 | 설명  |
| :--- | :--- |
| clearTimeout\(아이디\) | setTimeout을 취소합니다. |
| clearInterval\(아이디\) | setInterval을 취소합니다. |
| clearImmediate\(아이디\) | setImmediate를 취소합니다.  |

### \_\_filename과 \_\_dirname

 노드에서는 파일 간의 모듈 관계가 있는 경우가 많아 현재 파일의 경로나 파일명을 알아야하는 경우 다음과 같은 키워드를 사용할 수 있습니다. 

| 구분 | 설명 |
| :--- | :--- |
| \_\_filename | 해당 파일명에 대한 정보를 반환하는 키워드입니다. |
| \_\_dirname | 해당 파일의 경로에 대한 정보를 반환하는 키워드입니다.  |



