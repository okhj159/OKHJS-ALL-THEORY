# Server Side Rendering

## 목차
1. [개요](#개요)
2. [Next.js](#Next.js)

## 개요
- 

## Next.js
- App Router 버전
    - Getting Started
        - Installation
        - Project Structure
            - App Routing Conventions
                - Routing Files
                    - layout
                        -  세그먼트 및 해당 하위 항목에 대한 공유 UI
                    - page
                        - 경로의 고유한 UI 및 경로에 공개적으로 액세스 가능
                    - template
                        - Re-rendered layout
    - Building Your Application
        - 라우팅
            - 버전13에서 Next.js는 공유 레이아웃, 중첩 라우팅, 로딩 상태, 오류 처리 등을 지원하는 React Server Components를 기반으로
              구축된 새로운 App Router를 도입하였다.
            - Redirecting
                - Next에서 redirect를 핸들링하는 몇 가지 방법이 있다.
                  <img src="next/redirecting.png">
            - Route Handlers
            - Middleware
                - Matching paths
                    - 미들웨어는 프로젝트의 모든 루트에서 호출된다. 실행순서는 다음과 같다.
                      <img src="next/matching_paths.png">
                - NextResponse
                    - NextResponse API는 다음과 같은 일을 수행할 수 있다.
                        - 다른 URL으로 들어오는 요청을 redirect
                        - 주어진 URL을 표시한 응답을 rewrite
                        - API Routes, getServerSideProps, rewrite destination에 대해 request headers를 설정할 수 있다.
                        - 응답 쿠키를 설정
                        - 응답 헤더를 설정
                - Using Cookies
                    - Cookies는 일반 헤더이다. 요청 시 쿠키 헤더에 저장된다. 응답시에는 Set-Cookie에 있다.
                      Next.js는 cookies를 확장한 NextRequest와 NextResponse를 통해 cookies에 접근하고 조작할 수 있는 편리한 방법을 제공한다.
                    - 요청이 들어오는 경우, cookies는 다음 method와 함께 들어온다: get, getAll, set 그리고 delete cookies
                      has를 통해 cookie가 존재하는지 체크할 수 있고, clear를 통해 모든 cookie를 제거할 수 있다.
                    - 응답이 나가는 경우, cookie는 다음 method와 함께 작동한다: get, getAll, set 그리고 delete
        - Data Fetching
            - Server Actions and Mutations
                - Server Actions는 서버에서 실행되는 비동기적 함수들을 말한다. 이것들은 서버 및 클라이언트 구성 요소에서 Next.js 애플리케이션의
                  양식 제풀 및 데이터 변형을 처리하는 데 사용할 수 있다.
                - Convention
                    - server action은 리액트의 "use server" 지시문을 통해 정의될 수 있다. async function의 상단에 지시문을 배치하여 해당
                      기능을 서버 작업으로 표시하거나 별도의 파일 상단에 배치하여 해당 파일의 모든 내보내기를 서버 작업으로 표시할 수 있다.
        - 렌더링
            - 서버 컴포넌트
                - 정적 렌더링의 경우 라우트는 빌드 시 렌더링 되거나 데이터 재검증 후 백그라운드에서 렌더링 된다.
                - 동적 렌더링은 요청 시점에 렌더링 된다. 사용자 맞춤 데이터가 있거나 쿠키, URL searchParam과 같이 요청 시점에 알 수 있는 정보가 있는 경우 유용하다.
            - 클라이언트 컴포넌트
                - 클라이언트 컴포넌트는 state, effect, event listener를 사용할 수 있다.
                - 브라우저 API (ex.window, localStorage ...) 사용 가능하다.
    - Api Reference
        - File Conventions
            - page.js
                - route에 유일한 UI이다.
                - props
                    - params
                        - 루트 세그먼트부터 해당 페이지까지의 동적 경로 매개변수를 포함하는 객체이다
                          <img src="next/params.png">
                    - searchParams
                        - 검색 매개변수를 포함하는 객체
                          <img src="next/search_params.png">
        - next.config.js Options
            - appDir
            - assetPrefix
            - basePath
                - Next.js 어플리케이션 도메인의 sub-path를 배포하기 위해 basePath를 사용할 수 있다.
                - Links
                    - next/link와 next/router를 사용하여 linking을 할 때 basePath는 자동으로 적용된다.
                - Images
                    - next/image 컴포넌트를 사용할 때, src 앞에 basePath가 더해진다.
            - crossOrigin
            - distDir
                - .next 디렉토리 대신 사용할 특정한 디렉토리가 필요할 때 값을 넣으면 된다.
                - distDir은 프로젝트 디렉토리를 벗어날 수 없다. 예를 들어 `../build`와 처럼은 안 된다.
            - env
                - JavaScript bundle에 환경 변수를 더하기 위해서 사용할 수 있다.
            - eslint
            - exportPathMap
            - rewrites
                - Rewrites는 request path를 다른 destination path로 매핑시킬 수 있게 한다.
        - Edge Runtime
            - Next.js의 Edge Runtime은 표준 Web API를 근간으로 한다.
    - Architecture
- Pages Router 버전
    - getServerSideProps
        - next.js의 내장 함수로서, URL에서 동적으로 변수값을 가져올 수 있게 한다.
- 렌더링 방식
    - SSR(Server-Side-Rendering)
        - 요청에 따라 서버에서 html 페이지를 동적으로 렌더링하고 웹 브라우저로 전송할 수 있다.
          또한 서버에서 렌더링한 페이지에 스크립트 코드를 집어넣어서 나중에 웹 페이지를 동적으로 처리할 수도 있는데 이를 하이드레이션이라고 한다.
        - 중요한 데이터를 클라이언트에 노출할 필요가 없기 때문에 더 안전하다.
        - 봇, 웹 크롤러 같은 검색 엔진 웹 문서 수집기가 페이지를 렌더링할 필요가 없어, 웹 애플리케이션의 SEO 점수가 높아진다.
    - CSR(Client-Side-Rendering)
        - 클라이언트에서의 내비게이션은 브라우저 화면을 새로 고칠 필요 없이 다른 페이지로의 이등이 가능하다.
        - 웹 앱에서는 최소로 필요한 html 마크업만 렌더링한다.
        - 전체 렌더링 과정이 브라우저에서 일어나기 때문에 서버 부하가 감소한다. AWS Lamda와 Firebase와 같은 서버리스 환경에서 웹 앱을 제공할 수도 있다.

<hr />