# body-parser

## body-parser

**body-parser는 요청의 본문을 해석해주는 미들웨어**입니다. 보통 폼 데이터나 AJAX 요청의 데이터를 처리합니다. 다음과 같이 사용합니다. 

```javascript
...
const bodyParser = require("body-parser");
...
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({extended: false}));
...
```

 단, 익스프레스 4.16.0 버전부터는 body-parser의 일부 기능이 익스프레스에 내장되어 있어 굳이 설치하지 않고도 다음과 같이 사용할 수 있습니다.

```javascript
app.use(express.json());
app.use(express.urlencoded({ extended:false }));
```

 단, JSON이나 URL-encoded 형식의 본문 외에도 Raw, Text 형식의 본문을 추가로 해석해야 할 때 다음과 같이 지정해줍니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>app.use(bodyParser.raw())</b>
      </td>
      <td style="text-align:left">&#xBCF8;&#xBB38;&#xC774; &#xBC84;&#xD37C; &#xB370;&#xC774;&#xD130;&#xC77C;
        &#xB54C; &#xD574;&#xC11D;&#xD558;&#xB294; &#xBBF8;&#xB4E4;&#xC6E8;&#xC5B4;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>app.use(bodyParser.text())</b>
      </td>
      <td style="text-align:left">&#xBCF8;&#xBB38;&#xC774; &#xD14D;&#xC2A4;&#xD2B8; &#xB370;&#xC774;&#xD130;&#xC77C;
        &#xB54C; &#xD574;&#xC11D;&#xD558;&#xB294; &#xBBF8;&#xB4E4;&#xC6E8;&#xC5B4;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>app.use(express.json())</b>
      </td>
      <td style="text-align:left">JSON &#xD615;&#xC2DD;&#xC758; &#xB370;&#xC774;&#xD130; &#xC804;&#xB2EC;
        &#xBC29;&#xC2DD;&#xC744; &#xD574;&#xC11D;&#xD558;&#xB294; &#xBBF8;&#xB4E4;&#xC6E8;&#xC5B4;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>app.use(express.urlencoded({extended: false}));</b>
      </td>
      <td style="text-align:left">
        <p>&#xC8FC;&#xC18C; &#xD615;&#xC2DD;&#xC73C;&#xB85C; &#xB370;&#xC774;&#xD130;&#xB97C;
          &#xBCF4;&#xB0B4;&#xB294; &#xBC29;&#xC2DD;&#xC744; &#xD574;&#xC11D;&#xD558;&#xB294;
          &#xBBF8;&#xB4E4;&#xC6E8;&#xC5B4;</p>
        <p>&#xC8FC;&#xB85C; &#xD3FC; &#xC804;&#xC1A1;&#xC774; &#xC774;&#xB97C; &#xC790;&#xC8FC;
          &#xC0AC;&#xC6A9;&#xD55C;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>URL-cencoded방식의 **extended가 false이면 노드의 querystring을 사용**하여 쿼리스트링을 해석하고 **true면 qs모듈을 사용하여 쿼리스트링을 해석**합니다. 

{% hint style="info" %}
qs모듈은 내장 모듈이 아니라 npm 패키지이며, querystring 모듈의 기능을 조금 더 확장한 모듈입니다. 
{% endhint %}

