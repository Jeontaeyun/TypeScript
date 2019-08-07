---
description: 해당 페이지는 REST API를 설계하고 이를 문서화 하는 방법에 대해 정리한 페이지입니다.
---

# REST API 문서화

## RESTful API 문서화 방법

### RESTful API 문서화 예시

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAE30;&#xB2A5;</th>
      <th style="text-align:left">HTTP &#xBA54;&#xC11C;&#xB4DC;</th>
      <th style="text-align:left">HTTP ULR &amp; BODY</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xBAA8;&#xB4E0; &#xD68C;&#xC6D0; &#xC815;&#xBCF4; &#xC870;&#xD68C;</td>
      <td
      style="text-align:left">HTTP GET</td>
        <td style="text-align:left">http://www.connectdot.co.kr/users</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD2B9;&#xC815; &#xD68C;&#xC6D0; &#xC815;&#xBCF4; &#xC870;&#xD68C;</td>
      <td
      style="text-align:left">HTTP GET</td>
        <td style="text-align:left">http://www.connectdot.co.kr/users/:username</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD68C;&#xC6D0; &#xC815;&#xBCF4; &#xAC80;&#xC0C9;</td>
      <td style="text-align:left">HTTP GET</td>
      <td style="text-align:left">http://www.connectdot.co.kr/users?query=xxx</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD68C;&#xC6D0; &#xB4F1;&#xB85D;</td>
      <td style="text-align:left">HTTP POST</td>
      <td style="text-align:left">
        <p>http://www.connectdot.co.kr/users</p>
        <p>{</p>
        <p>&quot;name&quot;: &quot;terry&quot;</p>
        <p>...</p>
        <p>}</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD68C;&#xC6D0; &#xC0AD;&#xC81C;</td>
      <td style="text-align:left">HTTP DELETE</td>
      <td style="text-align:left">http://www.connectdot.co.kr/users/:username</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD574;&#xB2F9; &#xD68C;&#xC6D0; &#xC815;&#xBCF4; &#xBCC0;&#xACBD;</td>
      <td
      style="text-align:left">HTTP PUT</td>
        <td style="text-align:left">
          <p>http://www.connectdot.co.kr/users/:username</p>
          <p>{</p>
          <p>&quot;name&quot;: &quot;terry&quot;,</p>
          <p>&quot;address&quot;:&quot;seoul&quot;</p>
          <p>...</p>
          <p>}</p>
        </td>
    </tr>
  </tbody>
</table>

