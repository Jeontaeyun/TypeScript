---
description: >-
  리액트에 TypeScript를 적용하면 PropTypes등과 같이 타입을 State와 Props에 타입을 암시해주어야하는 것을 더 높은
  가독성과 함께 사용할 수 있습니다.
---

# 타입스크립트 + 리액트

## 타입스크립트 리액트 설정

 CRA\(create-react-app\)을 통해서 생성한 프로젝트의 jsx확장자를 **tsx**로 바꿔주며 다음과 같은 CRA 보일러플레이트로 손쉽게 프로젝트 환경을 구성할 수 있습니다.

```bash
$create-react-app (projectName) --scripts-version=react-scripts-ts
$create-react-app (projectName) --typescript
```

 기존에 진행하던 프로젝트에 TypeScript를 추가하고 싶다면 다음과 같이 해야합니다.

```bash
$yarn add typescript @types/node @types/react @types/react-dom @types/jest
$yarn add ts-loader -dev
```

이후 파일의 확장자를 .tsx로 바꿔준 후 서버를 실행하면 자동으로 tsconfig.json파일이 생성됩니다. 

### 리액트를 위한 tsconfig.json 설정

```javascript
{
  "compilerOptions": {
    // leave JSX as it is
    "jsx": "react",
    // resolve modules as you would expect
    "moduleResolution": "node",
    // leave imports as they are
    "module": "commonjs",
    // do not transpile stuff like classes, async/await, ...
    "target": "es5",
    "lib": [
      "es2015", "es6", "esnext", "dom"
    ],
    "allowJs": true,
    // produce a source map
    "sourceMap": true,
    "baseUrl": ".",
    "outDir": "dist",
    "paths": {
      "components/*": ["./src/components/*"],
      "containers/*": ["./src/containers/*"],
      "assets/*": ["./src/assets/*"],
      "constants/*": ["./constants/*"],
      "utils/*": ["./src/utils/*"]
    },
    "allowSyntheticDefaultImports": true,
    "keyofStringsOnly": true
  },
  "include": [
    "./src/**/*"
  ],
  "exclude": [
    "./node_modules/**/*"
  ]
}
```

### 타입스크립트를 위한 webpack.js 설정

```javascript
const path = require('path');

module.exports = {
  entry: {
    'vendor': ['react', 'react-dom'],
    'app': path.resolve(__dirname, '..', 'src', 'App.tsx'),
  },
  optimization: {
    splitChunks: {
      cacheGroups: {
        vendor: {
          chunks: 'initial',
          name: 'vendor',
          enforce: true,
        },
      },
    },
  },
  output: {
    filename: '[name].[chunkhash].js',
    chunkFilename: '[name].[chunkhash].chunk.js',
  },
  resolve: {
    extensions: ['.js', '.ts', '.tsx'],
    alias: {
      'components': path.resolve(__dirname, '..', 'src', 'components'),
      'containers': path.resolve(__dirname, '..', 'src', 'containers'),
      'assets': path.resolve(__dirname, '..', 'src', 'assets'),
    },
  },
  module: {
    rules: [
      {
        test: /\.(ts|tsx)$/,
        exclude: /node_modules/,
        use: [
          {
            loader: 'ts-loader',
          },
        ],
      },
    ],
  },
  // plugins
  plugins: [],
};
```

