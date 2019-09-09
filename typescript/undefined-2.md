# 타입스크립트 프로젝트 설정

## 타입스크립트 프로젝트 번들러

 번들링\(Bundling\)은 프로젝트의 다양한 파일\(리소스\)를 합쳐 Javascript, HTML, CSS 코드로 묶어주는 패키지를 말합니다. 타입스크립트 자체적으로 --out 옵션을 이용해 타입스크립트 파일을 번들링 할 수 있지만 다른 자원을 함께 번들링 하기 위해 **웹팩\(Webpack\)과 Parcel** 같은 번들러를 사용하는 것이 좋습니다.

{% hint style="info" %}
**번들링 Bundling**

 번들링은 쉽게 말해 프로젝트에 사용되는 다양한 파일을 모아서 배포 가능한 단위로 합치는 것을 말합니다. 즉, 모듈 간의 의존 관계를 파악해 정적 파일 형태로 빌드 결과를 생성합니다.
{% endhint %}

### 웹팩을 이용한 번들링 설정

 대표적인 번들러 웹팩을 이용해 프로젝트를 번들링 하기 위해서는 웹팩과 CLI환경을 설치해야합니다.

```bash
$npm i webpack webpack-cli
```

그 후 **웹팩 설정 파일\(webpack.config.js\)**을 다음과 같 설정해 줍니다. 

```javascript
const path = require("path");
module.exports = {
    entry: "시작할 파일 경로",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dianme, "dist")
    }
};
```

이 후 webpack명령어를 통해 웹팩 설정 파일에서 지정해준 엔트리 파일을 아웃풋 설정대로 번들링 해줍니다.

```bash
$webpack
```

### 타입스크립트 로더 설정

 웹팩의 추가 기능인 로더 중 ts-loader는 타입스크립트를 입력받아 tsconfig.json 파일을 기준으로 컴파일을 수행합니다.  따라서 타입스크립트 로더각 사용할 타입스크립트 설정 파일인 tsconfig.json파일을 작성해야 합니다. 

```javascript
// tsconfig.json
{
    "CompilerOptions": {
        "module" : "commonjs",
        "target" : "es5",
        "noImplicitAny" : false,
        "sourceMap" : false
    },
    "exclude" : [
        "node_modules"
    ]
}
```

 컴파일 될 때 node\_modules 디렉터리는 컴파일되지 않도록 추가해주어야 합니다. 또한 별도로 typescript 로컬 파일이 필요해 로컬 프로제트에 typescript를 설치합니다.

```bash
$npm i typescript --dev
```

 그 후 웹팩 설정 파일에 ts-loader를 추가합니다. 

```javascript
const path = require("path");
module.exports = {
    entry: "시작할 파일 경로",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dianme, "dist")
    },
    module : {
        loaders:[{
            test: /\.tsx?$/,
            laoder: "ts-loader",
            options : {
                transpileOnly :true
            }
        }]
    }
};
```

