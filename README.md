# Astro Starter Kit: Basics

```sh
npm create astro@latest -- --template basics
```

[![Astro Badge](https://img.shields.io/badge/Astro-BC52EE?logo=astro&logoColor=fff&style=plastic)](https://docs.astro.build/ko/editor-setup/)
[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/withastro/astro/tree/latest/examples/basics)
[![Open with CodeSandbox](https://assets.codesandbox.io/github/button-edit-lime.svg)](https://codesandbox.io/p/sandbox/github/withastro/astro/tree/latest/examples/basics)
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/withastro/astro?devcontainer_path=.devcontainer/basics/devcontainer.json)

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   └── Card.astro
│   ├── layouts/
│   │   └── Layout.astro
│   ├── pages/
│   │    └── index.astro
│   └── styles/
└── package.json
```

Astro는 `src/pages/` 디렉토리에서 `.astro` 또는 `.md` 파일을 찾습니다. 각 페이지는 파일 이름을 기반으로 경로로 노출됩니다.

`src/components/`에는 특별한 것이 없지만, Astro/React/Vue/Svelte/Preact의 구성 요소를 여기에 두는 것이 좋습니다.

이미지와 같은 모든 정적 자산은 `public/` 디렉토리에 배치할 수 있습니다.

## 🧞 Commands(terminal)

| Command                   | Action                                                                       |
| :------------------------ | :--------------------------------------------------------------------------- |
| `npm install`             | Installs dependencies                                                        |
| `npm i -D`                | --save-dev, 로컬 개발 환경에서만 사용, 개발시 의존성 패키지(devDependencies) |
| `npm i -S`                | --save, 프로덕션 환경에서 사용, 실행시 의존성 패키지(dependencies)           |
| `npm uninstall`           | --save, 프로덕션 환경에서 사용, 실행시 의존성 패키지(dependencies)           |
| `npm run dev`             | Starts local dev server at `localhost:4321`                                  |
| `npm run build`           | Build your production site to `./dist/`                                      |
| `npm run preview`         | Preview your build locally, before deploying                                 |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check`                             |
| `npm run astro -- --help` | Get help using the Astro CLI                                                 |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).

## 🧑‍🚀 VS Code Extensions

-   [Astro](https://marketplace.visualstudio.com/items?itemName=astro-build.astro-vscode)
-   [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)

## 🎁 Package

```bash
# 1. prettier(eslint, stylelint) configuration
$ npm i -D prettier eslint-config-prettier eslint-plugin-prettier stylelint-prettier

# 2. stylelint with scss
$ npm i -D stylelint stylelint-scss stylelint-selector-bem-pattern stylelint-order

# 3. 추가 config 패키지 설치 (standard rules, smacss property sort order)
$ npm i -D stylelint-config-standard-scss stylelint-config-property-sort-order-smacss stylelint-config-prettier-scss

# 4. tailwindCss
$ npx astro add tailwind
```

### eslint package설명

-   `eslint-config-prettier` : prettier와 출돌하는 eslint규칙을 비활성화하는 패키지
-   `eslint-plugin-prettier` : prettier를 eslint 규칙으로 실행하고 차이점을 eslint에게 전달하는 패키지

### stylelint package설명

-   `stylelint` : 기본 패키지
-   `stylelint-scss` : SCSS 파일에서 특정 규칙(@if, @else, @for, @each 등의 SCSS 제어문)을 적용
-   `stylelint-prettier` : prettier
-   `stylelint-order` : stylelint 에서 코드 스타일의 순서를 검사하고 관리
-   `stylelint-selector-bem-pattern` : bem 규칙
-   Config
    -   `stylelint-config-standard` : CSS의 표준 스타일 가이드에 따라 코드를 검사하고 포맷팅. 들여쓰기, 공백, 따옴표 등의 규칙을 - 적용하여 일관성을 유지
    -   `stylelint-config-recommended-scss, stylelint-config-standard-scss` : stylint에서 표준으로 제공하는 SCSS 규칙에 대한 패키지(recommended가 느슨한 rule, standard가 엄격한 rule)
    -   `stylelint-config-property-sort-order-smacss` : SMACSS 기반으로 속성 정렬, recommended style property sort order를 지원하는 패키지( style property sort order는 smacss, rational, recess 등)
    -   `stylelint-config-prettier` : stylelint 와 prettier 를 통합하여 코드 포맷팅을 관리
    -   `stylelint-config-prettier-scss` : prettier와 충돌되는 stylelint SCSS규칙을 비활성화하는 패키지이다.
    -   `stylelint-config-recess-order` : stylelint-order 플러그인의 설정을 미리 정의한 구성(config) 파일, 속성 선언 순서를 규칙 (만약 prettier를 사용중이라면 설치해주자)

### 도구 자동화

-   /.vscode/setting.json 추가
    -   따로 세팅을 해줘야 협업에 좋음

```json
{
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.tabSize": 4,
    "editor.insertSpaces": true,
    "css.validate": false,
    "scss.validate": false,
    "javascript.format.enable": false,
    "files.autoSave": "onFocusChange"

    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true, // eslint 자동 수정
        "source.fixAll.stylelint": true // stylelint 자동 수정
    },
    "editor.formatOnSave": true, // prettier 자동 수정,
    "stylelint.validate": ["css", "scss", ".module.scss"],
    "stylelint.enable": true,
    "eslint.alwaysShowStatus": true,
}
```

### [Style lint](https://stylelint.io/)

-   css 문법을 잡아주고, 코드 컨벤션 설정까지 가능한 도구

1. VSCode에서 Stylelint Extension 설치
2. 패키지 설치
3. 생성 : `.stylelintrc.json`
    > style lint의 rules 생성해주는 사이트 : [stylelint-config](https://maximgatilin.github.io/stylelint-config/)

```js
{
  "plugins": ["stylelint-scss", "stylelint-selector-bem-pattern", "stylelint-order", "stylelint-prettier"],
  "extends": [
    "stylelint-config-recess-order",
    "stylelint-config-standard",
    "stylelint-config-standard-scss",
    "stylelint-config-prettier-scss",
    "stylelint-config-property-sort-order-smacss",
    "stylelint-prettier/recommended"
    ],
  "rules": {
    "prettier/prettier": true,
    }
}
```

### [Eslint-astro](https://ota-meshi.github.io/eslint-plugin-astro/user-guide/)

-   자바스크립트 문법 에러를 표시하거나 코딩 컨벤션에 위배되는 코드, 안티 패턴을 자동 검출하는 도구

1. 설치

```bash
npm i -D eslint-plugin-astro
```

2. `.eslintrc.json` 설정

```js
{
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:prettier/recommended"
    ],
    "rules": {
        "no-var": "warn", // var 금지
        "no-multiple-empty-lines": "warn", // 여러 줄 공백 금지
        "no-console": ["warn", { "allow": ["warn", "error"] }], // console.log() 금지
        "eqeqeq": "warn", // 일치 연산자 사용 필수
        "dot-notation": "warn", // 가능하다면 dot notation 사용
        "no-unused-vars": "warn", // 사용하지 않는 변수 금지
        "react/destructuring-assignment": "warn", // state, prop 등에 구조분해 할당 적용
        "react/jsx-pascal-case": "warn", // 컴포넌트 이름은 PascalCase로
        "react/no-direct-mutation-state": "warn", // state 직접 수정 금지
        "react/jsx-no-useless-fragment": "warn", // 불필요한 fragment 금지
        "react/no-unused-state": "warn", // 사용되지 않는 state
        "react/jsx-key": "warn", // 반복문으로 생성하는 요소에 key 강제
        "react/self-closing-comp": "warn", // 셀프 클로징 태그 가능하면 적용
        "react/jsx-curly-brace-presence": "warn" // jsx 내 불필요한 중괄호 금지
    }
}
```

3. VS Code extension 설치

### [Prettier-astro](https://github.com/withastro/prettier-plugin-astro)

-   코드 포맷터

1. 설치

```bash
npm i -D prettier-plugin-astro
```

2. 생성 : .prettierrc.mjs

```mjs
export default {
    plugins: ["prettier-plugin-astro"],
    overrides: [
        {
            files: "*.astro",
            options: {
                parser: "astro",
            },
        },
    ],
};
```

3. VS Code extension 설치

> 자동으로 정렬

```json
// 1. vscode : settings.json
{
    "prettier.documentSelectors": ["**/*.astro"],
    "[astro]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    "stylelint.validate": ["scss", "css"]
}
```

### [tailwind Css](https://tailwindcss.com/docs/guides/astro)

-   코드 포맷터

1. 설치

```bash
npm i -D prettier-plugin-tailwindcss
```

2. 생성 : .prettierrc.mjs

```mjs
{
    plugins: ["prettier-plugin-tailwindcss"],
};
```

3. VS Code extension 설치
4. 사용법
    - [scss와 충돌 이슈](https://tailwindcss.com/docs/using-with-preprocessors#using-sass-less-or-stylus)
    - [container-queries](https://tailwindcss.com/docs/plugins#container-queries)
        - [plugin](https://github.com/tailwindlabs/tailwindcss-container-queries)

## 🚀 Scss Structure

```text
/
├── src/styles/
│    ├── abstracts/
│    │   : Configuration and helpers(utilities, helpers)
│    │   ├── _functions.scss
│    │   └── _mixins.scss
│    │
│    ├── base/
│    │   : boiler plate code(묻지도 따지지도 않고 별 수정없이 따라 적는 코드)
│    │   └── _typography.scss
│    │
│    ├── components/
│    │   : modules, 슬라이더, 로더, 위젯
│    │   ├── _buttons.scss
│    │   ├── _media.scss
│    │   ├── _carousel.scss
│    │   ├── _thumbnails.scss
│    │   └── _swiper.scss
│    │
│    ├── layout/
│    │   : partials, 전반적인 뼈대, 거시적
│    │   ├── _grid.scss
│    │   ├── _header.scss
│    │   ├── _footer.scss
│    │   ├── _sidebar.scss
│    │   ├── _forms.scss
│    │   └── _navigation.scss
│    │
│    ├── pages/
│    │   :
│    │   ├── _hera_.scss
│    │   └── _laneige.scss
│    │
│    ├── themes/
│    │   : dark, light 모드
│    │
│    ├── vendors/
│    │   : 외부 라이브러리와 프레임워크에서 나오는 모든 CSS 파일
│    │
└────└── _common.scss
         : 불러오기
```

## ✍ 참고자료

[초기세팅](https://official.palms.blog/initial-setting)
[css-in-js](https://velog.io/@parksil0/%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%97%90-%EC%BD%94%EB%93%9C-%EC%8A%A4%ED%83%80%EC%9D%BC-%EC%85%8B%ED%8C%85%ED%95%98%EA%B8%B0eslint-prettier-stylelint#css-in-js%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%A0-%EB%95%8C%EC%9D%98-stylelintrc-%ED%8C%8C%EC%9D%BC)

```

```
