# 노드 CLI 프로그램

## 노드 CLI 커맨드 

 **커맨드 라인 인터페이스\(Command Line Interface\)**는 터미널에서 사용하는 npm, create-react-app과 같은 명령어를 말합니다. 즉, 콘솔 창에서 프로그램을 수행하는 환경이라는 의미입니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>CLI</b> 
      </td>
      <td style="text-align:left">
        <p>&#xCF58;&#xC194; &#xCC3D;&#xC758; &#xBA85;&#xB839;&#xC5B4;&#xB97C; &#xAE30;&#xBC18;&#xC73C;&#xB85C;
          &#xCEF4;&#xD4E8;&#xD130;&#xB97C; &#xC81C;&#xC5B4;&#xD558;&#xB294; &#xC778;&#xD130;&#xD398;&#xC774;&#xC2A4;
          &#xBC29;&#xC2DD;</p>
        <p>Ex. &#xB9AC;&#xB205;&#xC2A4; &#xC258;, &#xCF58;&#xC194;, &#xBA85;&#xB839;
          &#xD504;&#xB86C;&#xD504;&#xD2B8; &#xB4F1;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>GUI</b>
      </td>
      <td style="text-align:left">
        <p>&#xC77C;&#xBC18;&#xC801;&#xC73C;&#xB85C; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
          PC&#xC640; &#xAC19;&#xC774; &#xADF8;&#xB798;&#xD53D; &#xAE30;&#xBC18;&#xC73C;&#xB85C;
          &#xCEF4;&#xD4E8;&#xD130;&#xB97C; &#xC81C;&#xC5B4;&#xD558;&#xB294; &#xC778;&#xD130;&#xD398;&#xC774;&#xC2A4;
          &#xBC29;&#xC2DD;</p>
        <p>Ex. &#xC708;&#xB3C4;&#xC6B0;, &#xB9E5; &#xC6B4;&#xC601; &#xCCB4;&#xC81C;,
          &#xC6F9; &#xC560;&#xD50C;&#xB9AC;&#xCF00;&#xC774;&#xC158; &#xB4F1;</p>
      </td>
    </tr>
  </tbody>
</table> 우리는 **커스터마이징 된 CLI 명령어를 만들어 개발의 효율을 높일 수 있습니다**. DRY\(Don't repeat Yoursllef\) 즉, 중복 배제가 프로그래머의 소양이라는 것을 기억합시다.

### 노드 CLI 커맨드 만드는 법

#### 01. package.json과 index.js 생성

```javascript
[package.json]
{
    "name" : : "component-cli",
    "version" : : "0.0.1",
    "description" : : "component generator cli program",
    "main" : : "index.js",
    "scripts" : : {
        "test" : "echo \"Error: no test specified\" && exit1"
    },
    "author" : : "Stark",
    "license" : : "MIT",
    "bin" : {
        "cli" : "./index.js"
    }
}
```

```javascript
[index.js]
#! /usr/bin/env node
cosole.log('Create Component');
```

{% hint style="info" %}
**\#! /usr/bin/env node**

리눅스나 맥 같은 유닉스 기반 운영체제에서는 해당 구문을 /usr/bin/env에 등록된 node 명령어로 이 파일을 실행하라는 뜻입니다. 윈도우 운영체제에서는 단순히 주석으로 취급합니다.
{% endhint %}

 위와 같이 프로그램을 작성한 후 해당 패키지를 전역 설치합니다.

```bash
$npm i -g packageName
```

{% hint style="info" %}
**전역 설치 \| Global Install**

보통 패키지를 전역 설치할 때는 명령어에 패키지명을 함께 적어주지만 현재 패키지를 전역 설치할 때는 적지 않습니다. 
{% endhint %}

 이 후 콘솔에 cli를 입력하면 해당 명령어가 실행됩니다. 

```bash
$cli
// Create Component
```

### 향상된 노드 CLI 커맨드 만드는 법

#### 01. 노드 내장 모듈 readline 사용하기



### Commander 라이브러리와, inquier, chalk 패키지 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>commander</b>
      </td>
      <td style="text-align:left">CLI&#xD504;&#xB85C;&#xADF8;&#xB7A8;&#xC744; &#xB9CC;&#xB4E4;&#xAE30; &#xC704;&#xD55C;
        &#xB300;&#xD45C;&#xC801;&#xC778; &#xB77C;&#xC774;&#xBE0C;&#xB7EC;&#xB9AC;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>inquirer</b>
      </td>
      <td style="text-align:left">CLI &#xD504;&#xB85C;&#xADF8;&#xB7A8;&#xACFC; &#xC0AC;&#xC6A9;&#xC790;
        &#xAC04;&#xC758; &#xC0C1;&#xD638; &#xC791;&#xC6A9;&#xC744; &#xB3D5;&#xB294;
        &#xD328;&#xD0A4;&#xC9C0;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>chalk</b>
      </td>
      <td style="text-align:left">
        <p>&#xCF58;&#xC194; &#xD14D;&#xC2A4;&#xD2B8;&#xC5D0; &#xC2A4;&#xD0C0;&#xC77C;&#xC744;
          &#xCD94;&#xAC00;&#xD558;&#xB294; &#xD328;&#xD0A4;&#xC9C0;.</p>
        <p>&#xB2E8;, &#xD130;&#xBBF8;&#xB110; &#xB9C8;&#xB2E4; &#xC9C0;&#xC6D0;&#xD558;&#xB294;
          &#xC0C9;&#xC774;&#xB098; &#xC2A4;&#xD0C0;&#xC77C;&#xC774; &#xB2E4;&#xB974;&#xBBC0;&#xB85C;
          &#xBAA8;&#xB4E0; &#xD658;&#xACBD;&#xC5D0;&#xC11C; &#xAC19;&#xAC8C; &#xB3D9;&#xC791;
          &#xD558;&#xC9C0;&#xB294; &#xC54A;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>{% hint style="info" %}
**npm 패키지**

 npm에는 서버를 위한 패키지뿐만 아니라 다양한 프로그램을 위한 패키지가 준비되어 있으므로 적극 활용하기 바랍니다. 
{% endhint %}

```javascript
#! /usr/bin/env node
const program = require('commander');
const inquirer = require('inquirer');
const reactCreator = require('./reactCreator');
const dirCreator = require('./dirCreator');
const path = require('path');
const fs = require('fs');
const chalk = require('chalk');

let triggered = false;
program.version('0.0.1', '-v, --version').usage('[options]');

program.command('*', { noHelp: true }).action(() => {
	console.log(chalk.red('\n해당 명령어를 찾을 수 없습니다.\n'));
	program.help();
});

program.parse(process.argv);

if (!triggered) {
	inquirer
		.prompt([
			{
				type: 'list',
				name: 'type',
				message: '\n 어떤 컴포넌트를 생성할 지 선택하세요',
				choices: [ '프레젠트 컴포넌트', '컨테이너 컴포넌트' ]
			},
			{
				type: 'input',
				name: 'name',
				message: '\n 파일의 이름을 입력하세요(복수 가능)',
				default: 'Comp'
			},
			{
				type: 'input',
				name: 'directory',
				message: '\n 파일이 위치할 경로를 입력해주세요(./src에서 시작)',
				default: './UI_Components'
			},
			{
				type: 'confirm',
				name: 'confirm',
				message: '\n생성하시겠습니까?'
			}
		])
		.then((answers) => {
			const { confirm, name, type, directory } = answers;
			const nameArray = name.split(' ');
			nameArray.forEach((item) => {
				dirCreator.mkdir(`src/${directory}/${item}`);
				const pathToFile = path.join(`src/${directory}/${item}`, `/index.js`);
				const pathToScss = path.join(`src/${directory}/${item}`, `/index.scss`);
				if (dirCreator.exist(pathToFile)) {
					console.error(chalk.red(`\n 이미 해당 ${item} 파일이 존재합니다.\n`));
				} else {
					if (confirm) {
						if (type === '컨테이너 컴포넌트') {
							fs.writeFileSync(pathToFile, reactCreator.reactContainerTemplate(item));
							fs.writeFileSync(pathToScss, '');
							console.log(chalk.green(`\n ${item} 컴포넌트가 생성되었습니다.\n`));
						} else if (type === '프레젠트 컴포넌트') {
							fs.writeFileSync(pathToFile, reactCreator.reactPresentTemplate(item));
							fs.writeFileSync(pathToScss, '');
							console.log(chalk.green(`\n ${item} 컴포넌트가 생성되었습니다. \n`));
						}
					}
				}
			});
			console.log(chalk.bgGreen.rgb(00, 00, 00).bold(`\n 모든 컴포넌트가 생성되었습니다. \n`));
		});

```

#### 

