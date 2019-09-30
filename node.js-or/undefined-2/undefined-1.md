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

### module과 exports

 module과 exports는 모듈을 만들어주는 객체입니다. 다음과 같이 사용할 수 있습니다.

```javascript
module.exports = {...모듈 객체};
exports.moduleFunction = () => {...};
exports.hi = "안녕하세요";
```

module.exports은 한 번에 대입하는 방법이고, exports는 객체에 하나씩 넣는 방법을 말합니다. module.exports와 exports가 같은 객체를 참조하기에 위와 같이 동작합니다. 

### process

 **process는 현재 실행되고 있는 노드 프로세스에 대한 정보**를 담고 있습니다. process에는 다양한 속성이 담겨있습니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">process.version</td>
      <td style="text-align:left">&#xC124;&#xCE58;&#xB41C; &#xB178;&#xB4DC;&#xC758; &#xBC84;&#xC804;&#xC744;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">process.arch</td>
      <td style="text-align:left">&#xD504;&#xB85C;&#xC138;&#xC11C; &#xC544;&#xD0A4;&#xD14D;&#xCCD0; &#xC815;&#xBCF4;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;. arm, x64&#xB4F1; CPU &#xC544;&#xD0A4;&#xD14D;&#xCCD0;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">process.platform</td>
      <td style="text-align:left">
        <p>&#xC6B4;&#xC601;&#xCCB4;&#xC81C; &#xD50C;&#xB7AB;&#xD3FC; &#xC815;&#xBCF4;&#xB97C;
          &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>- win32, linux, darwin, freebsd &#xB4F1;&#xC758; &#xAC12;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">process.pid</td>
      <td style="text-align:left">
        <p>&#xD604;&#xC7AC; &#xD504;&#xB85C;&#xC138;&#xC11C;&#xC758; &#xC544;&#xC774;&#xB514;&#xB97C;
          &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E4;&#xC911; &#xD504;&#xB85C;&#xC138;&#xC2A4; &#xD658;&#xACBD;&#xC5D0;&#xC11C;
          &#xAD6C;&#xBD84;&#xC5D0; &#xB3C4;&#xC6C0;&#xC774; &#xB429;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">process.uptime()</td>
      <td style="text-align:left">&#xD504;&#xB85C;&#xC138;&#xC2A4;&#xAC00; &#xC2DC;&#xC791;&#xB41C; &#xD6C4;
        &#xD750;&#xB978; &#xC2DC;&#xAC04;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.
        &#xB2E8;&#xC704;&#xB294; &#xCD08;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">process.execPath</td>
      <td style="text-align:left">&#xB178;&#xB4DC;&#xC758; &#xACBD;&#xB85C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">process.cwd()</td>
      <td style="text-align:left">&#xD604;&#xC7AC; &#xD504;&#xB85C;&#xC138;&#xC2A4;&#xAC00; &#xC2E4;&#xD589;&#xB418;&#xB294;
        &#xC704;&#xCE58;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">process.cpuUsage()</td>
      <td style="text-align:left">&#xD604;&#xC7AC; cpu &#xC0AC;&#xC6A9;&#xB7C9;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">process.env</td>
      <td style="text-align:left">
        <p>&#xD504;&#xB85C;&#xC138;&#xC2A4;&#xC5D0;&#xC11C; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
          &#xC911;&#xC694;&#xD55C; &#xD658;&#xACBD; &#xBCC0;&#xC218;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xD658;&#xACBD;&#xBCC0;&#xC218;&#xB294; .env &#xD30C;&#xC77C;&#xC5D0;
          &#xBCF4;&#xAD00;&#xD558;&#xC5EC; &#xBCF4;&#xC548;&#xC5D0; &#xC8FC;&#xC758;&#xB97C;
          &#xAE30;&#xC6B8;&#xC5EC;&#xC57C; &#xD569;&#xB2C8;&#xB2E4; .</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">process.nextTick(&#xCF5C;&#xBC31;)</td>
      <td style="text-align:left">
        <p>&#xC774;&#xBCA4;&#xD2B8; &#xB8E8;&#xD504;&#xAC00; &#xB2E4;&#xB978; &#xCF5C;&#xBC31;
          &#xD568;&#xC218;&#xB4E4; &#xBCF4;&#xB2E4; nextTick&#xC758; &#xCF5C;&#xBC31;
          &#xD568;&#xC218;&#xB97C; &#xC6B0;&#xC120;&#xC73C;&#xB85C; &#xCC98;&#xB9AC;&#xD558;&#xB3C4;&#xB85D;
          &#xD569;&#xB2C8;&#xB2E4; .</p>
        <p>- setImmediate&#xB098; setTimeout&#xBCF4;&#xB2E4; &#xBA3C;&#xC800; &#xC2E4;&#xD589;&#xB429;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">process.exit(&#xCF54;&#xB4DC;)</td>
      <td style="text-align:left">
        <p>&#xC2E4;&#xD589; &#xC911;&#xC778; &#xB178;&#xB4DC; &#xD504;&#xB85C;&#xC138;&#xC2A4;&#xB97C;
          &#xC885;&#xB8CC;&#xD569;&#xB2C8;&#xB2E4;. &#xC11C;&#xBC84;&#xC5D0; &#xC774;
          &#xD568;&#xC218;&#xB97C; &#xC0AC;&#xC6A9;&#xD558;&#xBA74; &#xC11C;&#xBC84;&#xAC00;
          &#xBA48;&#xCD94;&#xBBC0;&#xB85C; &#xAC70;&#xC758; &#xC0AC;&#xC6A9;&#xD558;&#xC9C0;
          &#xC54A;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E4;&#xB9CC;, &#xC11C;&#xBC84;&#xAC00; &#xC544;&#xB2CC; &#xB3C5;&#xB9BD;&#xC801;&#xC73C;&#xB85C;
          &#xB3CC;&#xC544;&#xAC00;&#xB294; &#xD658;&#xACBD;&#xC5D0;&#xC11C; &#xD504;&#xB85C;&#xADF8;&#xB7A8;&#xC758;
          &#xC885;&#xB8CC;&#xB97C; &#xC704;&#xD574; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
          &#xACBD;&#xC6B0;&#xAC00; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>