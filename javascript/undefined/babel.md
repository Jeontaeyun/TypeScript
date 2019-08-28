# 바벨 Babel

## 바벨 Babel.js

 **바벨\(BabelJS\)**는 **ES2015+코드를 ES5로 바꿔주는 자바스크립트 라이브러리**입니다. 

ES2015+는 구형 브라우저에서 지원하지 않는 **호환성**의 문제가 발생합니다. 아직 IE의 유저가 많기 때문에 Babel을 통해서 ES5 언어로 컴파일 해주어야 합니다.

### 바벨 설치 

```text
$npm install -dev @babel/cli @babel/core @babel/preset-env @babel/preset-stage-2
```

 바벨을 설치하여 CLI 명령어를 통해서 컴파일 할 수 있지만 package.json 파일에 설정하는 것이 더 편합니다. 

### 바벨 Package.json 설정 

01. .babelrc 파일을 만들어 설치한 preset을 연결합니다.

```javascript
// .babelrc
{
    "preset" : [
        ["@babel/preset-env", {"targets":{ "browsers": ["last 2 versions", ">= 5% in KR"] } }],
        ["@babel/preset-stage-2",{"decoratorsLegacy" : true}]
    ]
}
```

 위의 @babel/preset-env는 바벨이 동작할 사전 설정을 정의하며, 최신 두 버전과 한국에서 5%이상 점유율을 차지하는 모든 브라우저를 지원하라고 설정해준 것 입니다.

02. package.json 파일 설정

```javascript
{
    "scripts" : {
        "build" : "babel src -d lib"
    }
}
```

 babel을 실행하고 src 폴더에 있는 최신 자바스크립트 코드를 컴파일하여 결과를 lib폴더에 넣으라는 뜻입니다.

### 바벨 babel-polyfill 

 바벨을 사용하면 새로운 문법을 구형 자바스크립트 문법으로만 바꿔줍니다. 다만 ES2015 이ㅣ후의 새로운 객체\(Promise, Map, Set 등등\)과 새로운 메소드를 이용할 수 없습니다. 따라서 babel-polyfill을 사용해야 합니다.

```text
$npm install @babel/polyfill
```

babel-polyfill을 사용하고 싶다면 제일 먼저 로딩되는 스크립트 제일 위에 추가해주어야 합니다. 이를 넣으면 컴파일러가 자동으로 적용해줍니다.   


#### babel-polyfill 웹팩 설정

 만약 웹팩을 사용한다면, 웹팩의 entry에 파일을 설정해도 됩니다. 

```javascript
webpack.config.js

{
    entry: ['@babel/polyfill' , './app.js']
}
```

