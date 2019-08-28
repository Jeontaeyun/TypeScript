# 타입스크립트 환경 설정

## 타입스크립트 설치 및 환경설정

### 타입스크립트 설치

 타입스크립트는 Node.js의 npm\(Node.js Package Manager\)을 이용해서 설치할 수 있습니다.

```bash
$npm i -g typescript
$npm outdated -g typescript
$tsc -v
$tsc index.ts
```

### 타입스크립트 ECMA스크립트 버전별 컴파일\(-t 옵션\)

```bash
$tsc hello.ts -t ES5
```

| 구분  | 설명 |
| :--- | :--- |
| ES3 | 기본값 |
| ES5 | 설정 가능 |
| ES6\(ES2015\) | 설정 가능 |
| ES2016 | 설정 가능 |
| ES2017 또는 ESNext | 최신 버전의 ECMA스크립트  |

### tsc 명령어의 변경 감지 기능

```text
$tsc hello.ts -watch
```

 감시 상태에서 파일의 내용이 수정되면 컴파일을 수행하겠다는 로그를 출력하고 컴파일을 수행합니다. 

### tsconfig.json 파일을 이용한 컴파일

  tsconfig.json 파일은 타입스크립트 프로젝트를 컴파일할 때 컴파일 설정 정보를 담는 설정 파일입니다. 이를 이용해 타입스크립트를 컴파일할 때 필요한 설정을 관리할 수 있습니다. 

```bash
$tsc --init
```

 위의 명령어를 통해서 tsconfig.json파일을 생성할 수 있습니다. tsconfig.json파일이 있으면 tsc 명령어 실행시 tsconfig.json 파일의 설정을 읽어 들여 자동으로 컴파일 합니다. 

 주의할 점은 **tsconfig.json 파일이 위치한 경로가 타입스크립트 프로젝트의 루트 경로**가 된다는 것 입니다. 

```javascript
{
    "compilerOptions":{
        /* Basic Options */
        "outDir" : "./dist-outdir",
        "target" : "es5",
        "module", "commonjs",
        ...
        // "sourceMap": true,
        ...
        "strict" : true,
        // "noImplicitAny" : true,
        "esModuleInterop" : true,
        ...
    },
    "files": [
        ...컴파일 할 파일 
    ],
    "include": [
        ...컴파일 시 사용할 디렉토리
    ],
    "exclude": [
        ...컴파일 시 제외할 디렉토리
    ]
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xC635;&#xC158;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">outDir</td>
      <td style="text-align:left">&#xCEF4;&#xD30C;&#xC77C; &#xD6C4; &#xCD9C;&#xB825;&#xD560; &#xB514;&#xB809;&#xD130;&#xB9AC;&#xB97C;
        &#xC124;</td>
    </tr>
    <tr>
      <td style="text-align:left">target</td>
      <td style="text-align:left">&#xCEF4;&#xD30C;&#xC77C; &#xD6C4; &#xBCC0;&#xD658;&#xB420; ECMA&#xC2A4;&#xD06C;&#xB9BD;&#xD2B8;
        &#xBC84;&#xC804;</td>
    </tr>
    <tr>
      <td style="text-align:left">module</td>
      <td style="text-align:left">&#xBAA8;&#xB4C8; &#xD615;&#xC2DD;&#xC744; &#xC9C0;&#xC815;</td>
    </tr>
    <tr>
      <td style="text-align:left">sourceMap</td>
      <td style="text-align:left">&#xCEF4;&#xD30C;&#xC77C; &#xD6C4; &#xB9F5;(map)&#xD30C;&#xC77C; &#xC0DD;&#xC131;
        &#xC5EC;&#xBD80; &#xACB0;&#xC815;</td>
    </tr>
    <tr>
      <td style="text-align:left">strict</td>
      <td style="text-align:left">true&#xC77C; &#xACBD;&#xC6B0; &#xC5C4;&#xACA9;&#xD55C; &#xD0C0;&#xC785;
        &#xAC80;&#xC0AC; &#xBAA8;&#xB4DC;&#xB97C; &#xD65C;&#xC131;&#xD654; &#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">noImplicitAny</td>
      <td style="text-align:left">
        <p>any&#xD0C0;&#xC785;&#xC73C;&#xB85C; &#xC554;&#xBB35;&#xC801; &#xD615;&#xBCC0;&#xD658;
          &#xC5EC;&#xBD80;&#xB97C; &#xACB0;&#xC815; &#xAE30;&#xBCF8;&#xAC12;&#xC740;
          false</p>
        <p>false&#xC774;&#xBA74; &#xD0C0;&#xC785;&#xC2A4;&#xD06C;&#xB9BD;&#xD2B8;&#xC5D0;&#xC11C;
          &#xD0C0;&#xC785;&#xC744; &#xC9C0;&#xC815;&#xD558;&#xC9C0; &#xC54A;&#xC740;
          &#xBCC0;&#xC218;&#xB294; &#xC790;&#xB3D9;&#xC73C;&#xB85C; any&#xD0C0;&#xC785;&#xC73C;&#xB85C;
          &#xCD94;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">esModuleInterop</td>
      <td style="text-align:left">ECMA&#xC2A4;&#xD06C;&#xB9BD;&#xD2B8; &#xBAA8;&#xB4C8;&#xACFC; &#xC0C1;&#xD638;
        &#xC6B4;&#xC6A9;&#xC131;&#xC744; &#xAC00;&#xB2A5;&#xD558;&#xAC8D; &#xD558;&#xB294;
        &#xC18D;&#xC131;&#xC73C;&#xB85C; true&#xBA74; CommonJS&#xBAA8;&#xB4C8;&#xC744;
        &#xB514;&#xD3F4;&#xD2B8; &#xBAA8;&#xB4C8;&#xCC98;&#xB7FC; &#xD638;&#xCD9C;&#xD560;
        &#xC218; &#xC788;</td>
    </tr>
  </tbody>
</table> 타입 스크립트는 타입을 추가함으로써 예상치 못한 오류를 컴파일 단계에서 발견할 수 있는 것이 특징입니다. 

맵 파일은 컴파일 과정에서 타입스크립트 파일과 자바스크립트 파일 간의 연결 정보를 담고 있습니다.

### ts-node 모듈

 ts-node패키지는 노드를 이용해 타입스크립트 파일을 실행할 수 있는 환경을 제공합니다. 해당 패키지를 통해 컴파일하고 실행하는 과정을 더욱 간소화할 수 있습니다.

```bash
$tsc hello.ts
$node hello.js
위의 과정을 아래와 같이 줄여줄 수 있습니다.
$ts-node hello.ts
```

### VS Code 태스크러너 설정

 VS Code에서 빌드를 수행하는 단축키는 **&lt;Ctrl+Shift+B&gt;**입니다. 해당 키를 눌렀을 때 **빌드 작업을 자동화하려면 태스크 러너를 설정**해야 합니다.

1. &lt;Ctrl+Shift+P&gt;를 눌러 커맨드 팔레트\(Command Palette\) 호출
2. Configure Task 로 .vscode/tasks.json 파일 생성
3. 태스크러너 커스터 마이징 

```javascript
// 타입스크립트를 위한 task.json파일 설정
{
    "version": "2.0.0",
    "tasks": [
        {
            "type": "typescript",
            "tsconfig": "tsconfig.json",
            "options": "watch",
            "problemMatcher" :[
                "$tsc-watch"
            ]
        },
        {
            "type": "typescript",
            "tsconfig": "tsconfig.json",
            "problemMatcher":[
                "$tsc"
            ]
        }
    ]
}
```

