# Build Tools

## 목차
1. [개요](#개요)
2. [Linters and Formatters](#Linters-and-Formatters)
3. [Module Bundlers](#Module-Bundlers)

## 개요
- 

## Linters and Formatters

### Prettier
- About
- Usage
    - Install
        - 첫번째로 Prettier를 설치한다.
            `yarn add --dev --exact prettier`
        - Config 파일을 생성한다.
            `node --eval "fs.writeFileSync('.prettierrc','{}\n')"`
        - .prettierignore 파일을 생성한다.
            `node --eval "fs.writeFileSync('.prettierignore','# Ignore artifacts:\nbuild\ncoverage\n')"`
        - 이제 Prettier로 모든 파일을 포매팅한다.
            `yarn prettier . --write`
        - `prettier --write .`는 모든것을 포매팅하는 좋은 도구이지만, 큰 프로젝트에는 시간이 좀 걸릴 수 있다. `prettier --write app/`와 같은
        특정한 디렉토리나 `prettier --write app/components/Button.js`와 같이 특정 파일에 사용하는 것이 더 나을 수 있다. 혹은 prettier --write `"app/**/*.test.js"`와 같이 glob을 사용하는것도 좋다.
        - 만약 CI 설정이 있다면 다음을 실행하여 모든 사람이 Prettier를 실행하도록 하라. 이렇게 하면 병합 충돌 및 기타 협업 문제가 방지된다.
            `npx prettier . --check`
        - --check는 --write와 유사하지만 덮어쓰지 않고 포맷을 체크하기만 한다. 
        - Set up yout editor
            - command line으로 하는 포매팅을 좋은 방법이기는 하지만 키보드 단축키를 사용하거나 파일을 저장할 때마다 자동으로 편집기에서 Prettier를 실행하면
            Prettier를 최대한 활용할 수 있다. 코딩하는 동안 줄이 너무 길어져서 화면에 맞지 않을 때, 키를 누르면 마법처럼 여러 줄로 줄바꿈되는 것을 볼 수 있다.
            또는 코드를 붙여넣고 들여쓰기가 엉망이 되면 Prettier가 편집기를 벗어나지 않고도 수정해 준다.
        - ESLint
            - ESLint를 사용하는 경우 eslint-config-prettier를 설치하여 ESLint와 Prettier가 서로 잘 어울리도록 한다. 불필요하거나 Prettier와 충돌할 수 있는
            모든 ESLint 규칙을 끈다. 
        - Git hooks
    - Ignoring Code
        - Ignoring Files: .prettierignore
        - JavaScript
        - JSX
        - HTML
        - CSS
        - Markdown
        - YAML
        - Command Line File Patterns
    - Integrating with Linters
        - Linter는 일반적으로 코드 품질 규칙뿐만 아니라 스타일 규칙도 포함한다. Prettier를 사용할 때 대부분의 스타일 규칙은 불필요하지만 더 나쁜 점은
        Prettier와 충동할 수 있다는 것이다. Prettier는 코드 포매팅 문제에 사용하고 Linter는 코드 품질 문제에 사용한다.
        - 다행히 Prettier와 충돌하거나 불필요한 규칙을 해제하는 것은 다음과 같은 사전 제작된 구성을 사용하여 쉽게 가능하다.
            - eslint-config-prettier
    - Pre-commit Hook
        - Option 1. lint-staged
        - Option 2. Husky.Net
        - Option 3. git-format-staged
        - Option 4. Shell script
    - CLI
    - API
    - Browser
- Configuring Prettier
    - Options
    - Configuration File
    - Sharing configurations
- Editors
- Misc

### ESLint
- USE ESLINT IN YOUR PROJECT
    - Getting Started
    - Core Concepts
        - Glossary
    - Configure ESLint
        - Configuration Files
        - Configure Language Options
- EXTEND ESLINT
- INTEGRATE ESLINT
- CONTRIBUTE TO ESLINT
- MAINTAIN ESLINT

## Module Bundlers

### vite
-

### Webpack
-

<hr />