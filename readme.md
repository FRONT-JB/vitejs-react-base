# ViteJS, React, Typescript

**[Loadable Components](https://medium.com/greendatakr/loadable-components-881e936aa8fa)**

**[React Router Config](https://velog.io/@naseriansuzie/TIL32)**

<br />

## Package

1.  `react & react-dom` : **기본 코어**
2.  `react-router` : **라우팅 구성**
3.  `@loadable/component` : **동적 경로 로딩**
4.  `classnames` : **향상된 className 작성**
5.  `react-router-config` : **향상된 리액트 라우터 라우팅 구성 패키지**
6.  `eslint, lint-staged, husky, prettier` : **코드 컨벤션**
7.  `eslint-config-alloy` : **ESLint 구성 플러그인**

<br />

## Setup

    npm init @vitejs/app fe-project-base --template react-ts

<br />

    yarn add react-router @loadable/component classnames react-router-config

<br />

    yarn add -D eslint lint-staged husky@4.3.8 prettier

> 위의 종속 항목을 설치한 후 **cat .git/hooks/pre-commit** 명령어를 통해 정상적으로 설치되었는지 확인합니다. 파일이 없으면 설치가 실패한 것이므로 다시 설치해야 합니다.

```js
// Package.json
{
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{ts,tsx}": [
      "eslint --cache --fix",
      "git add"
    ],
    "src/**/*.{js,jsx}": [
      "eslint --cache --fix",
      "git add"
    ]
  },
}
```

<br />

**.editorconfig**

    root = true

    [*]
    indent_style = space
    indent_size = 2
    end_of_line = lf
    charset = utf-8
    trim_trailing_whitespace = true
    insert_final_newline = true

<br />

**vscode/settings.json**

```js
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.tslint": true
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "typescript.tsdk": "node_modules/typescript/lib",
  "[typescriptreact]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

<br />

**eslint + prettier**

    yarn add -D eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier eslint-plugin-prettier eslint-config-prettier

> **`@typescript-eslint/parser`** : typescript-estree를 활용한 타입스크립트용 ESLint 파서(ESLint 기본 파서인 espree를 대신함)
>
> **` @typescript-eslint/eslint-plugin`** : TypeScript관련 linting 규칙을 처리하는 플러그인
>
> **`plugin:prettier/recommended`** : eslint-plugin-prettier + eslint-config-prettier 동시 적용
>
> **`prettier/@typescript-eslint`** : prettier 규칙과 충돌하는 @typescript-eslint/eslint-plugin 규칙 비활성화

<br />
