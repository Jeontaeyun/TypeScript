# 모듈화 \| Modulization

## 모듈화 

 노드는 코드를 모듈로 만들 수 있다는 점에서 브라우저의 자바스크립와 다릅니다. 

{% hint style="info" %}
**모듈**이란 특정한 기능을 하는 함수나 변수들의 집합입니다. 
{% endhint %}

 모듈로 만들어 두면 여러 프로그램에 해당 모듈을 재 사용할 수 있습니다. 자바스크립트에서 코드를 재사용하기 위해 함수로 만드는 것과 비슷합니다. 

### 모듈화 방법 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">const &#xBCC0;&#xC218;&#xBA85; = require(&apos;&#xBAA8;&#xB4C8;&#xD30C;&#xC77C;&apos;)</td>
      <td
      style="text-align:left">&#xBAA8;&#xB4C8;&#xC744; &#xBD88;&#xB7EC;&#xC640; &#xBCC0;&#xC218;&#xC5D0;
        &#xB300;&#xC785;&#xD574;&#xC8FC;&#xB294; &#xBC29;&#xBC95; require &#xBA54;&#xC18C;&#xB4DC;&#xB97C;
        &#xC774;&#xC6A9;&#xD55C;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">module.exports = &#xBAA8;&#xB4C8;</td>
      <td style="text-align:left">&#xBAA8;&#xB4C8;&#xC744; &#xB0B4;&#xBCF4;&#xB0B4;&#xB294; &#xBC29;&#xBC95;
        &#xB0B4;&#xBCF4;&#xB0B4;&#xB294; &#xBAA8;&#xB4C8;&#xC740; &#xBCC0;&#xC218;&#xAC00;
        &#xB420; &#xC218; &#xC788;&#xACE0; &#xAC1D;&#xCCB4;&#xAC00; &#xB420; &#xC218;
        &#xC788;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">exports.&#xC18D;&#xC131; = &#xD568;&#xC218;(){}</td>
      <td style="text-align:left">
        <p>&#xD2B9;&#xC815; &#xC774;&#xB984;&#xC73C;&#xB85C; &#xBAA8;&#xB4C8;&#xC744;
          &#xB0B4;&#xBCF4;&#xB0B4;&#xB294; &#xBC29;&#xBC95;&#xC785;&#xB2C8;&#xB2E4;.
          {&#xBAA8;&#xB4C8;1, &#xBAA8;&#xB4C8;2} &#xB4F1; &#xB514;&#xC2A4;&#xD2B8;&#xB7ED;&#xCCD0;&#xB9C1;&#xC744;
          &#xD1B5;&#xD574; &#xD574;&#xB2F9; &#xBAA8;&#xB4C8;&#xC744; &#xBD88;&#xB7EC;&#xC62C;
          &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
        <p>Exports&#xAC1D;&#xCCB4;&#xC5D0; &#xC18D;&#xC131;&#xC744; &#xCD94;&#xAC00;&#xD574;&#xC8FC;&#xB294;
          &#xBC29;&#xBC95;</p>
      </td>
    </tr>
  </tbody>
</table>여러 파일에 걸쳐 재사용되는 함수나 변수들을 모듈로 만들어두면 편리합니다. 그러나 모듈이 많아지고, 모듈 간의 관계가 얽히게 되면 구조를 파악하기 어렵다는 단점도 있습니다. 

노드의 대부분의 파일은 다른 파일을 모듈로 사용하고 있으므로 모듈을 만들고 사용하는 방법을 꼭 알아두어야 합니다. 

