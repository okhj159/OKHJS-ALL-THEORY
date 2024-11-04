# Bonus Content

## 목차
1. [개요](#개요)
2. [Storybook](#Storybook)
3. [monorepo](#monorepo)
4. [BaaS](#BaaS)
5. [Cloud](#Cloud)

## 개요
- 

## Storybook
- Guides
    - Get started
        - Get started with Storybook
            - What is Storybook?
                - Storybook은 독립적으로 UI component와 page를 구축하기 위한 프론트엔드 workshop 이다.
        - Why Storybook?
        - Frameworks
            - Next.js
            - React & Webpack
    - Testing
- Tutorials
    - Intro to Storybook
    - Design System for Developers
    - UI Testing Handbook
    - Visual Testing Handbook

## monorepo
- 하나의 저장소에 여러 프로젝트를 관리하는 방식
- 특징
    - 프로젝트 간의 의존성을 관리하기 쉽다.
    - 프로젝트 간의 코드를 공유하기 쉽다.
    - 프로젝트 간의 버전을 관리하기 쉽다.
    - 프로젝트 간의 빌드와 테스트를 쉽게 할 수 있다.
    - 프로젝트 간의 배포를 쉽게 할 수 있다.
    
### TurboRepo
- Introduction
    - What is TurboRepo?
        - JavaScript 및 TypeScript 코드베이스를 위한 고성능 빌드 시스템. 모노레포를 확장하도록 설계되었으며 단일 패키지 작업 공간 에서 워크플로도 더 빠르게 만든다.
    - The monorepo problem
        - Monorepos에는 다양한 이점이 있지만, 확장하는데 어려움이 있다. 각 workspace에는 테스트 도구, linting, 빌드 프로세스들이 있다. 하나의 모노레포에는 수천개의 실행 문제가 있다.
    - The monorepo solution
        - Turborepos가 monorepo의 확장 문제를 해결할 수 있다. 
        - Turborepo는 최대 속도로 task를 예약하고 사용가능한 모든 코어에서 작업을 병렬화 한다.
- Crafting your repository
    - Structuring a repository
    - Managing dependencies
    - Creating an internal Package
    - Configuring tasks
    - Running tasks
    - Caching
    - Developing applications
    - Using environment variables
    - Constructing CI
- 기타
    - 빌드 시스템
    - 모노레포를 확장하도록 설계되었으며 단일 패키지 작업 공간 에서 워크플로도 더 빠르게 만든다.

## BaaS
- BaaS(Backend-as-a-Service)
- 개발자가 백엔드 인프라를 직접 구축하지 않고도 애플리케이션을 만들 수 있게 해주는 클라우드 서비스 모델
- 주요 기능
    - 데이터베이스 관리
    - 사용자 인증
    - 푸시 알림
    - 파일 저장소
    - API 호스팅
    - 서버리스 함수 실행
### Firebase
- Fundametals
  - Get started with Firebase
    - Add Firebase to an app
      - Apple platforms (iOS+)
        1. Firebase 프로젝트 만들기
          - Firebase Console에서 프로젝트 추가를 클릭한다.
          - 메시지가 표시되면 Firebase 약관을 검토하고 이에 동의한다.
          - 계속을 클릭한다.
          - (선택사항) 다음 Firebase 제품의 사용 환경을 최적화하려면 프로젝트에 Google 애널리틱스를 설정한다.
          - 프로젝트 만들기를 클릭한다. 기존 Google Cloud 프로젝트를 사용할 경우에는 Firebase 추가를 클릭한다.
        2. Firebase에 앱 등록
          - Firebase Console로 이동한다.
          - 프로젝트 개요 페이지 중앙에 있는 iOS+ 아이콘을 클릭하여 설정 워크플로를 시작한다. Firebase 프로젝트에 앱을 이미 추가한 경우 앱 추가를 클릭하여 플랫폼
          옵션을 표시한다.
          - 번들 ID 필드에 앱의 번들 ID를 입력한다.
            - 번들 ID는 무엇이며 어디에서 찾을 수 있는가?
              - 번들 ID는 Apple 생태계에서 애플리케이션능 고유하게 식별하는 역할을 한다.
              - 번들 ID 찾기: Xcode에서 프로젝트를 열고 프로젝트 탐색기에서 최상위 앱을 선택한 다음 General(일반) 탭을 선택한다.
              Bundle Identifier(번들 식별자) 필드의 값이 번들 ID이다.(예: com.yourcompany.yourproject)
              - 번들 ID 값은 대소문자를 구분하며 Firebase 프로젝트에 등록한 후에는 해당 Firebase 앱의 번들 ID 값을 변경할 수 없다.
          - (선택사항) 다른 앱 정보(앱 닉네임 및 App Store ID)를 입력한다.
            - Firebase에서 앱 닉네임과 App Store ID는 어떻게 사용되나?
              - 앱 닉네임: 닉네임은 편의상 지정하는 내부용 식별자로 Firebase Console에서 본인만 볼 수 있다.
              - App Store ID: Firebase 동적 링크에서 사용자를 App Store 페이지로 리디렉션하고 Google 애널리틱스에서 Google Ads로 전환 이벤트를 가져오는데
              사용된다. 앱에 아직 App Store ID가 없으면 나중에 프로젝트 설정에서 ID를 추가할 수 있다.
          - 앱 등록을 클릭한다.
        3. Firebase 구성 파일 추가
          - GoogleService-Info.plist 다운로드를 클릭하여 Firebase Apple 플랫폼 구성 파일(GoogleService-Info.plist)을 가져온다.
            - 이 구성 파일에 대해 알아야 할 사항은 무엇인가?
              - Firebase 구성 파일에는 고유하지만 보안 비밀은 아닌 프로젝트 식별자가 있다.
              - 언제든지 다시 Firebase 구성 파일을 다운로드할 수 있다.
              - 구성 파일 이름에 (2) 같은 문자가 추가되지 않았는지 확인한다.
          - 구성 파일을 Xcode 프로젝트의 루트로 이동한다. 메시지가 표시되면 모든 대상에 구성 파일을 추가하도록 선택한다.
          - 프로젝트에 번들 ID가 여러 개 있으면 객 앱에 자체 GoogleService-Info.plist 파일이 포함되도록 각 번들 ID를 Firebase console에서 등록된 앱과 연결해야 한다.
        4. 앱에 Firebase SDK 추가
          - 앱 프로젝트를 연 상태로 Xcode에서 File(파일) > Add Packages(패키지 추가)로 이동한다.
          - 메시지가 표시되면 Firebase Apple 플랫폼 SDK 저장소를 추가한다.
            - `https://github.com/firebase/firebase-ios-sdk`
          - 사용할 SDK 버전을 선택한다.
          - 사용할 Firebase 라이브러리를 선택한다. Firebase 프로젝트에 Google 애널리틱스가 사용 설정되어 있으면 FirebaseAnalytics를 추가해야 한다. IDFA 수집 기능이
          없는 애널리틱스의 경우 대신 FirebaseAnalyticsWithoutAdId를 추가한다.
        5. 앱에서 Firebase 초기화
          - 마지막 단계는 애플리케이션 초기화 코드를 추가하는 것이다. 앱에 Firebase를 추가할 때 이 단계를 이미 완료했을 수 있다.
          - UIApplicationDelegate의 FirebaseCore 모듈과 앱 대리자가 사용하는 다른 Firebase 모듈을 가져온다. 예를 들어 Cloud Firestore와 인증을
          사용하려면 다음과 같이 가져온다.
            - ```
              // SwiftUI

              import SwiftUI
              import FirebaseCore
              import FirebaseFirestore
              import FirebaseAuth
              ```
          - 앱 대리자의 application(_:didFinishLaunchingWithOptions:)메서드에서 FirebaseApp 공유 인스턴스를 구성한다.
            - ```
              // SwiftUI

              // Use Firebase library to configure APIs
              FirebaseApp.configure()
              ```
          - SwiftUI를 사용하는 경우 앱 대리자를 만들고 UIApplicationDelegateAdaptor 또는 NSApplicationDelegateAdaptor를 통해 App구조체에 연결해야 한다.
          앱 대리자 재구성도 중지해야 한다.
            - ```
              @main
              struct YourApp: App {
                // register app delegate for Firebase setup
                @UIApplicationDelegateAdaptor(AppDelegate.self) var delegate

                var body: some Scene {
                  WindowGroup {
                    NavigationView {
                      ContentView()
                    }
                  }
                }
              }

              ```
          - Google 애널리틱스용 Firebase SDK를 포함한 경우 앱을 실행하여 Firebase를 성공적으로 설치했다는 확인을 Firebase Console에 보낼 수 있다.
      - Android
      - Web
        1. Firebase 프로젝트 만들기 및 앱 등록
          - Firebase 프로젝트 만들기
            - Firebase Console에서 프로젝트 추가를 클릭한다.
            - 메시지가 표시되면 Firebase 약관을 검토하고 이에 동의한다.
            - 계속을 클릭한다.
            - (선택사항) 다음 Firebase 제품의 사용 환경을 최적화하려면 프로젝트에 Google Analytics를 설정한다.
            - 프로젝트 만들기를 클릭한다. 기존 Google Cloud 프로젝트를 사용하는 경우에는 Firebase 추가를 클릭한다.
          - 앱 등록
            - Firebase Console의 프로젝트 개요 페이지 중앙에 있는 웹 아이콘을 클릭하여 설정 워크플로를 시작한다.
            - 앱의 닉네임을 입력한다.
            - 앱 등록을 클릭한다.
            - 화면에 표시된 안내에 따라 앱에 Firebase SDK를 추가하고 초기화한다.
        2. SDK 설치 및 Firebase 초기화
          - npm을 사용하여 Firebase를 설치한다
            - `npm install firebase`
          - 앱에서 Firebase룰 초기화하고 Firebase 앱 객체를 만든다.
            - ```
              import { initializeApp } from 'firebase/app';
              // TODO: Replace the following with your app's
              const firebaseConfig = {
                //...
              }

              const app = initializeApp(firebaseConfig);
              ```
        3. 앱에서 Firebase에 액세스
          - Firebase 서비스 (예: cloud Firestore, Authentication, Realtime Database, Remote Config 등)은 개별적으로 가져올 수 있다.
          - 아래 예는 Cloud Firestore Lite SDK를 사용한 데이터 목록이다.
            - ```
              import { initializeApp } from 'firebase/app';
              import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
              // Follow this pattern to import other Firebase services
              // import { } from 'firebase/<service>';

              // TODO: Replace the following with your app's Firebase project configuration
              const firebaseConfig = {
                //...
              }

              const app = initializeApp(firebaseConfig);
              const db = getFirestore(app);

              // Get a list of cities from your database
              async function getCities(db) {
                const citiesCol = collection(db, 'cities');
                const citySnapshot = await getDocs(citiesCol);
                const cityList = citySnapshot.docs.map(doc => doc.data());
                return cityList
              }

              ```
        4. 크기 축소를 위해 모듈 번들러(webpack/Rollup) 사용
  - Manage your Firebase projects
    - Understand Firebase projects
      - Firebase 프로젝트 설정 및 앱 등록
        - Firebase Console에서 Firebase 프로젝트를 설정하고 앱을 등록할 수 있다. (고급 사용 사례의 경우 Firebase Management REST API 또는 Firebase CLI).
        프로젝트를 설정하고 앱을 등록할 때 조직과 관련하여 몇 가지 결정을 내리고 Firebase 관련 구성 정보를 로컬 프로젝트에 추가해야 한다.
        - 프로덕션 앱의 경우 명확한 개발 워크플로를 설정해야 하며 대개 여러 환경을 사용한다.
      - Firebase 프로젝트와 상호작용
        - Firebase 콘솔
        - Firebase CLI(명령줄 도구)
        - Firebase Management REST API
      - Firebase 프로젝트 식별자
        - Firebase 프로젝트는 프로젝트 이름, 프로제그 번호, 프로젝트 ID 비롯한 다양한 식별자를 사용하여 Firebase 백엔드와 다양한 개발자 인터페이스에서 식별할 수 있다.
        - 프로젝트 이름
          - 프로젝트를 만들 때 프로젝트 이름을 제공해야 한다. 이 식별자는 내부 전용 이름 Firebase 콘솔, Google Cloud 콘솔, Firebase CLI가 있다. 프로젝트 이름은
          공개적으로 표시되는 Firebase나 Google Cloud 제품, 서비스 또는 리소스에서 노출되지 않으며 단순히 다양한 프로젝트를 보다 간편하게 구분하는 용도로 사용된다.
        - 프로젝트 번호
          - Firebase 프로젝트 (및 연결된 Google Cloud 프로젝트)에 프로젝트 번호이다. 이 번호는 Google에서 할당하여 전역적으로 고유한 프로젝트의 정규 식별자이다.
          통합을 구성하거나 Firebase, Google 또는 타사 서비스에 API 호출 시 이 식별자를 사용한다.
            - 프로젝트 번호 찾기
              - 다음 옵션 중 하나를 사용하여 Firebase 프로젝트의 프로젝트 번호를 찾는다.
              - Firebase 콘솔 사용: 프로젝트 설정으로 이동한다. 상단 창에 프로젝트 번호가 표시된다.
              - Firebase CLI 사용: `firebase projects:list`를 실행한다. 프로젝트 번호가 계정과 연결된 모든 Firebase 프로젝트와 함께 표시된다.
              - Firebase Management REST API 사용: `projects.list`를 호출한다. 응답 본문에서는 `FirebaseProject`객체에 프로젝트 번호가 포함된다.
            - API 호출 및 프로젝트 번호
              - 대부분의 경우 API 호출 시 프로젝트의 고유 식별자를 포함해야 한다. 많은 API가 프로젝트 ID를 허용하지만 Firebase, Google 또는 타사 서비스에 API 호출 시
              프로젝트 번호를 사용하는 것이 좋다.
        - 프로젝트 ID
          - Firebase 프로젝트 (및 연결된 Google Cloud 프로젝트)에 프로젝트 ID이다. 이 ID는 Google 서비스 전반에 걸쳐 프로젝트에 대해 사용자가 정의한 모든 Firebase 및
          Google Cloud Firebase 프로젝트를 만들면 Firebase에서 자동으로 프로젝트에 고유 ID를 할당하지만 개발자가 설정 중에 수정할 수 있다. 일반적으로 이 식별자는 프로젝트를
          참조하기 위한 편의성 별칭으로 취급된다.
            - 프로젝트 ID 찾기
            - Firebase 리소스 및 프로젝트 ID
            - Firebase CLI 및 프로젝트 ID
            - API 호출 및 프로젝트 ID
      - Firebase 구성 파일 및 객체
        - Firebase 프로젝트에 앱을 등록하면 Firebase Console에서 로컬 앱 디렉터리에 직접 추가하는 Firebase 구성 파일(Apple/Android 앱) 또는 구성 객체(웹 앱)을 제공한다.
          - Apple의 경우 GoogleService-Info.plist 구성 파일을 추가한다.
          - Android의 경우 google-services.json
          - 웹 앱의 경우 Firebase 구성 객체를 추가한다.
        - Firebase 구성 파일 또는 객체는 앱을 특정 Firebase 프로젝트 및 리소스(데이터베이스, 스토리지 버킷 등)에 연결한다. 이 구성에는 Firebase Server API와 통신하고
        Firebase 프로젝트 및 Firebase 앱과 클라이언트 데이터를 연결하기 위해 Firebase 및 Google 서비스에 필요한 매개변수인 Firebase옵션이 포함된다. 필요한 최소
        Firebase옵션은 다음과 같다.
          - API 키: 비공개 사용자 데이터에 액세스할 필요가 없는 특정 API를 호출할 떄 사용되는 간단한 암호화된 문자열(예시 값: AIzaSyDOCAbC123dEf456GhI789jKl012-MnO)
          - 프로젝트 ID: 모든 Firebase 및 Google Cloud에서 프로젝트의 사용자 정의 고유 식별자이다. 이 식별자는 일부 Firebase 리소스의 URL 또는 이름에 표시될 수 
          있지만 일반적으로 프로젝트를 참조하기 위한 편의성 별칭으로 취급된다. (예시 값: myapp-project-123)
          - 애플리케이션 ID(AppID): 모든 Firebase에서 Firebase 앱의 고유 식별자로, 형식은 플랫폼에 따라 다르다.
            - Firebase Apple 앱: GOOGLE_APP_ID(예시 값: 1:1234567890:ios:321abc456def7890). Apple 번들 ID가 아니다.
            - Firebase Android 앱: mobilesdk_app_id(예시 값: 1:1234567890:android:321abc456def7890). Android 패키지 이름 또는 Android 애플리케이션 ID가 아니다.
            - Firebase 웹 앱: appId(예시 값: 1:65211879909:web:3ae38ef1cdcb2e01fe5f0c)
        - 주의: 앱의 Firebase 구성 파일 또는 객체를 직접 수정하지 않는 것이 좋다. 이러한 필수 Firebase 옵션에 대해 유효하지 않거나 누락된 값으로 앱을 초기화하면 최종
        사용자에게 심각한 문제가 발생할 수 있다.
    - Set up development workflows
    - Configure multiple projects
    - Select locations for products & resources
  - Platforms and frameworks
- Build
  - Overview
  - Emulator Suite
  - Authentication
    - iOS+
      - Sign in With a pre-built UI
        - 시작하기 전에
          1. Apple 프로젝트에 Firebase를 추가한다.
          2. Podfile에 FirebaseUI를 추가한다.
            - `pod 'FirebaseUI'`
            - 원하는 경우 사용할 인증 구성요소와 제공업체만 추가할 수 있다.
              ```
              pod 'FirebaseUI/Auth'

              pod 'FirebaseUI/Google'
              pod 'FirebaseUI/Facebook'
              pod 'FirebaseUI/OAuth' # Used for Sing in with Apple, Twitter, etc
              pod 'FirebaseUI/Phone'
              ```
          3. 아직 Firebase 프로젝트에 앱을 연결하지 않았다면 Firebase Console에서 연결한다.
        - 로그인 방법 설정
          - 이메일 주소 및 비밀번호
            - Firebase Console에서 인증 섹션을 열고 이메일 및 비밀번호 인증을 사용 설정한다.
          - 이메일 링크 인증
            1. Firebase Console에서 인증 섹션을 연다. 로그인 방법 탭에서 이메일/비밀번호 제공업체를 사용 설정한다. 이메일 링크 로그인을 사용하려면
            이메일/비밀번호 로그인이 사용 설정되어야 한다.
            2. 같은 섹션에서 이메일 링크(비밀번호가 없는 로그인) 로그인 방법을 사용 설정하고 저장을 클릭한다.
            3. FIREmailLinkAuthSignInMethod로 FUIEmailAuth 인스턴스를 초기화하면 이메일 링크 로그인을 사용 설정할 수 있다. handleCodeInApp이 true로
            설정된 유효한 FIRActionCodeSettings 객체도 제공해야 한다.
              - ```
                var actionCodeSettings = ActionCodeSettings()
                actionCodeSettings.url = URL(string: "https://example.appspot.com")
                actionCodeSettings.handleCodeInApp = true
                actionCodeSettings.setAndroidPackageName("com.firebase.example", installIfNotAvailable: false, minimumVersion: "12")

                let provider = FUIEmailAuth(authUI: FUIAuth.defaultAuthUI()!,
                                            signInMethod: FIREmailLinkAuthSignInMethod,
                                            forceSameDevice: false,
                                            allowNewEmailAccounts: true,
                                            actionCodeSetting: actionCodeSettings)
                ```
            
            1. 또한 초기화 메서드에 전달할 URL을 허용해야 한다. 이 URL을 허용하려면 Firebase Console에서 인증 섹션을 연다. 로그인 방법 탭에 있는 승인된 도메인에 해당
            URL을 추가한다.
            2. 딥 링크가 포착되면 이를 처리할 수 있도록 인증 UI로 전달해야 한다.
              - FUIAuth.defaultAuthUI()!.handleOpen(url, sourceApplication: sourceApplicaion)

            1. FirebaseUI-iOS의 이메일 링크 로그인은 FirebaseUI-Android 및 FirebaseUI-web과 호환되므로 FirebaseUI-Android에서 흐름을 시작한 사용자가
            링크를 열고 FirebaseUI-web으로 로그인을 완료할 수 있다. 이와 역순으로 진행되는 흐름 역시 가능하다.
          - Apple
            1. Firebase Apple 계정으로 로그인 가이드의 시작하기 전에 및 Apple의 익명 처리된 데이터 요구사항 준수 섹션을 따르시오
            2. Apple 계정으로 로그인 기능을 자격 파일에 추가한다.
            3. Apple 로그인용으로 구성된 OAuth 제공업체 인스턴스를 초기화한다.
              - provider = FUIOAuth.appleAuthProvider()
          - Google
          - Twitter
          - 전화번호
        - 로그인
          - FirebaseUI 로그인 흐름을 시작하려면 먼저 FirebaseUI를 초기화한다.
            ```
            import FirebaseAuthUI

            /* ... */

            FirebaseApp.configure()
            let authUI = FUIAuth.defaultAuthUI()
            // You need to adopt a FUIAuthDelegate protocol to receive callback
            authUI.delegate = self
            ```
          - 그런 다음 지원하고자 하는 로그인 방법을 사용하도록 FirebaseUI를 구성한다.
            ```
            import FirebaseAuthUI
            import FirebaseFacebookAuthUI
            import FirebaseGoogleAuthUI
            import FirebaseOAuthUI
            import FirebasePhoneAuthUI

            let providers: [FUIAuthProvider] = [
              FUIGoogleAuth(),
              FUIFacebookAuth(),
              FUITwitterAuth(),
              FUIPhoneAuth(authUI:FUIAuth.defaultAuthUI()),
            ]
            self.authUI.providers = providers
            ```
          - Google 또는 Facebook 로그인을 사용 설정했다면 Google 및 Facebook 로그인 흐름의 결과에 대한 핸들러를 구현한다.
            ```
            func application(_ app: UIApplication, open url: URL,
                options: [UIApplicationOpenURLOptionKey : Any]) -> Bool {
              let souceApplication = option[UIApplicationOpenURLOptionsKey.sourceApplication] as! String?
              if FUIAuth.defaultAuthUI()?.handleOpen(url, sourceApplication: sourceApplication) ?? false {
                return true
              }
              // other URL handling goes here.
              return false
            }
            ```
          - 마지막으로 FUIAuth애서 AuthViewController의 인스턴스를 가져온다. 그런 다음 앱의 첫 번째 뷰 컨트롤러로 표시하거나 앱의 다른 뷰 컨트롤러로 표시할 수 있다.
            ```
            로그인 방법 선택기를 가져오는 방법은 다음과 같다.
            let authViewController = authUI.authViewController()

            전화번호 로그인만 사용하려면 전화번호 로그인 보기를 바로 표시할 수 있다.
            let phoneProvider = FUIAuth.defaultAuthUI().providers.first as! FUIPhoneAuth
            phoneProvider.signIn(withPresenting: currentlyVisibleController, phoneNumber: nil)
            ```
          - 인증 번호를 표시하고 사용자가 로그인한 후 결과가 `didSingInWithUser:error:` 메서드의 FirebaseUI 인증 대리자에게 반환된다.
            ```
            func authUI(_ authUI: FUIAuth, didSignInWith user: FIRUser?, error: Error?) {
              // handle user and error as necessary
            }
            ```
        - 로그아웃
          - FirebaseUI는 Firebase 인증은 물론 모든 소셜 ID 공급업체에서 로그아웃시키는 편리한 방법을 제공한다.
      - Get Started(Apple 플랫폼에서 Firebase 인증 시작하기)
        - Firebase에 앱 연결
          1. Firebase SDK를 설치한다.
          2. Firebase Console에서 Firebase 프로젝트에 앱을 추가한다.
        - 앱에 Firebase Authentication 추가
          1. 앱 프로젝트를 연 상태로 Xcode에서 File(파일) > Add Packages(패키지 추가)로 이동한다.
          2. 메시지가 표시되면 Firebase Apple 플랫폼 SDK 저장소를 추가한다.
            `https://github.com/firebase/firebase-ios-sdk.git`
          3. Firebase Authentication 라이브러리를 선택한다.
          4. 타겟 빌드 설정의 Other Linker Flags(기타 링커 플래그) 섹션에 -ObjC 플래그를 추가한다.
          5. 완료되면 Xcode가 백그라운드에서 자동으로 종속 항목을 확인하고 다운로드하기 시작한다.
        - (선택사항) Firebase Local Emulator Suite으로 프로토타입 제작 및 테스트
        - Firebase SDK 초기화
          - 우선 앱 대리자에서 Firebase SDK를 가져온다.
            `import FirebaseCore`
          - 그런 다음 `application:didFinishLaunchingWithOptions:`메서드에서 FirebaseApp객체를 초기화한다.
            ```
            // Use Firebase library to configure APIs
            FirebaseApp.configure()
            ```
        - 인증 상테 수신 대기
          - 각각의 앱 뷰에서 앱에 로그인한 사용자에 대한 정보를 얻기 위해 FIRAuth 객체와 리스너를 연결한다. 이 리스너는 사용자의 로그인 상태가 변경될 때마다 호출된다.
          - 뷰 컨트롤러의 viewWillAppear 메서드에서 리스너를 연결한다.
            ```
            handle = Auth.auth().addStateDidChangeListener { auth, user in
              // ...
            }
            ```
          - 뷰 컨트롤러의 viewWillDisappear 메서드에서 리스너를 분리한다.
            `Auth.auth().removeStateDidChangeListener(handle!)`
        - 신규 사용자 가입
          - 신규 사용자가 자신의 이메일 주소와 비밀번호를 사용해 앱에 가입할 수 있는 양식을 만든다. 사용자가 양식을 작성하면 사용자가 입력한 이메일 주소와 비밀번호의 유효성을
          검사한 후 createUser 메서드에 전달한다.
            ```
            Auth.auth().createUser(withEmail: email, password: password) { authResult, error in
              // ...
            }
            ```
        - 기존 사용자 로그인
          - 기존 사용자가 자신의 이메일 주소와 비밀번호를 사용해 로그인할 수 있는 양식을 만든다. 사용자가 양식을 작성하면 signIn 메서드를 호출한다.
            ```
            Auth.auth().signIn(withEmail: email, password: password) { [weak self] authResult, error in
              guard let strongSelf = self else { return }
              // ...
            }
            ``` 
        - 사용자 정보 가져오기
          - 사용자가 로그인되면 사용자에 대한 정보를 가져올 수 있다. 예를 들어 인증 상태 리스너에서 다음을 수행한다.
            ```
            if let user = user {
              // The user's ID, unique to the Firebase project.
              // Do NOT use this value to authenticate with your backend server,
              // if you have one. Use getTokenWithCompletion:completion: instead.
              let uid = user.uid
              let email = user.email
              let photoURL = user.photoURL
              var multiFactorString = "MultiFactor: "
              for info in user.multiFactor.enrolledFactors {
                multiFactorString += info.displayName ?? "[DisplayName]"
                multiFactorString += " "
              }
              // ...
            }
            ```
      - Manage Users
        - 사용자 생성
        - 현재 로그인한 사용자 가져오기
        - 사용자 프로필 가져오기
        - 제공업체의 사용자 프로필 정보 가져오기
        - 사용자 프로필 업데이트하기
        - 사용자 이메일 주소 설정하기
        - 사용자에게 인증 메일 보내기
        - 사용자 비밀번호 설정하기
        - 비밀번호 재설정 이메일 보내기
        - 사용자 삭제
        - 사용자 재인증하기
        - 사용자 계정 가져오기
    - Android
    - Web
      - Sign in with a pre-built UI
        - FirebaseUI 초기화
          - SDK를 가져온 후 인증 UI를 초기화한다.
            - ```
              // Initialize the FirebaseUI Widget using Firebase.
              var ui = new firebaseui.auth.AuthUI(firebase.auth());
              ```
        - 로그인 방법 설정
          - 이메일 주소 및 비밀번호
            - Firebase Console에서 인증 섹션을 열고 이메일과 비밀번호 인증을 사용 설정한다.
            - FirebaseUI signInOptions 목록에 이메일 제공업체 ID를 추가한다.
              - ```
                ui.start('#firebaseui-auth-container', {
                  signInOptions: [
                    firebase.auth.EmailAuthProvider.PROVIDER_ID
                  ],
                });
                ```
            - 선택사항: 사용자가 표시 이름을 입력하도록 EmailAuthProvider를 구성할 수 있다(기본값: true).
              - ```
                ui.start('#firebaseui-auth-container', {
                  signInOptions: [
                    {
                      provider: firebase.auth.EmailAuthProvider.PROVIDER_ID,
                      requireDisplayName: false
                    }
                  ]
                });
                ```
          - 이메일 링크 인증
            - Firebase console에서 인증 섹션을 연다. 로그인 방법 탭에서 이메일/비밀번호 제공업체를 사용 설정한다. 이메일 링크 로그인을 사용하려면 이메일/비밀번호 로그인을
            사용 설정해야 한다.
            - 같은 섹션에서 이메일 링크(비밀번호가 없는 로그인) 로그인 방법을 사용 설정하고 저장을 클릭한다.
            - FirebaseUI signInOptions 목록에 이메일 제공업체 ID와 이메일 링크 signInMethod를 추가한다.
              - ```
                ui.start('#firebaseui-auth-container', {
                  signInOptions: [
                    {
                      provider: firebase.auth.EmailAuthProvider.PROVIDER_ID,
                      signInMethod: firebase.auth.EmailAuthProvider.EMAIL_LINK_SIGN_IN_METHOD
                    }
                  ],
                })
                ```
            - (단일 페이지 앱과 관련해) 조건부로 로그인 UI를 렌더링하는 경우 ui.isPendingRedirect()를 사용하여 이 URL이 이메일 링크를 사용하는 로그인에 해당하며
            로그인을 완료하려면 UI를 렌더링해야 하는지 감지한다. 
              - ```
                // Is there an email link sign-in?
                if(ui.isPendingRedirect()) {
                  ui.start('#firebaseui-auth-container', uiConfig);
                }
                // This can also be done via:
                if(firebase.auth().isSignInWithEmailLink(window.location.href)) {
                  ui.start('#firebaseui-auth-container', uiConfig);
                }
                ```
            - 선택사항
          - OAuth 제공업체(Google, Facebook, Twitter, GitHub)
          - 전화번호
        - 로그인
          - FirebaseUI 로그인 흐름을 시작하려면 기본 Auth 인스턴스를 전달하여 FirebaseUI 인스턴스를 초기화한다.
            - ```
              // Initialize the FirebaseUI Widget using Firebase
              var ui = new firebaseui.auth.AuthUI(firebase.auth());
              ```
          - FirebaseUI 로그인 위젯을 렌더링할 HTML 요소를 정의한다.
            - ```
              <!-- The surrounding HTML is left untouched by FirebaseUI.
                  Your app may use that space for branding, controls and other customizations.-->
              <h1>Welcome to My Awesome App</h1>
              <div id="firebaseui-auth-container"></div>
              <div id="loader">Loading...</div>
              ``` 
          - 지원되는 제공업체, UI 맞춤설정, 성공 콜백 등의 FirebaseUI 구성을 지정한다.
            - ```
              var uiConfig = {
                callbacks: {
                  signInSuccessWithAuthResult: function(authResult, redirectUrl) {
                    // User successfully signed in.
                    // Return type determines whether we continue the redirect automatically
                    // or whether we leave that to developer to handle.
                    return true;
                  },
                  uiShown: function() {
                    // The widget is rendered.
                    // Hide the loader.
                    document.getElementById('loader').style.display = 'name';
                  }
                },
                // Will use popup for IDP Providers sign-in flow instead of the default, redirect.
                signInFlow: 'popup',
                signInSuccessUrl: '<url-to-redirect-to-on-success>',
                signInOptions: [
                  // Leave the lines as is for the providers you want to offer your users.
                  firebase.auth.GoogleAuthProvider.PROVIDER_ID,
                  firebase.auth.FacebookAuthProvider.PROVIDER_ID,
                  firebase.auth.TwitterAuthProvider.PROVIDER_ID,
                  firebase.auth.GithubAuthProvider.PROVIDER_ID,
                  firebase.auth.EmailAuthProvider.PROVIDER_ID,
                  firebase.auth.PhoneAuthProvider.PROVIDER_ID
                ],
                // Terms of service url.
                tosUrl: '<your-tos-url>',
                // Privacy policy url.
                privacyPolicyUrl: '<your-privacy-policy-url>'
              };
              ```
          - 마지막으로 FirebaseUI 인증 인터페이스를 렌더링한다.
            - ```
              // The start method will wait until the DOM is loaded.
              ui.start('#firebaseui-auth-container', uiConfig);
              ```
      - Get Started
        - Authentication SDK 추가 및 초기화
          - 아직 진행하지 않았다면 Firebase JS SDK를 설치하고 Firebase를 초기화한다.
          - Firebase Authentication JS SDK를 추가하고 Firebase Authentication를 초기화한다.
            - ```
              import { initializeApp } from "firebase/app";
              import { getAuth } from "firebase/auth";

              // TODO: Replace the following with your app's Firebase project configuration
              // See: https://firebase.google.com/docs/web/learn-more#config-object
              const firebaseConfig = {
                // ...
              };

              // Initialize Firebase
              const app = initializeApp(firebaseConfig);

              // Initialize Firebase Authentication and get a reference to the service
              const auth = getAuth(app);
              ```
        - 신규 사용자 가입
          - 신규 사용자가 자신의 이메일 주소와 비밀번호를 사용해 앱에 가입할 수 있는 양식을 만듭니다. 사용자가 양식을 작성하면 사용자가 입력한 이메일 주소와 비밀번호의
          유효성을 검사한 수 createUserWithEmailAndPassword 메서드에 전달한다.
            - ```
              import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

              const auth = getAuth();
              createUserWithEmailAndPassword(auth, email, password)
                .then((userCredential) => {
                  // Signed up
                  const user = userCredential.user;
                  // ...
                })
                .catch((error) => {
                  const errorCode = error.code;
                  const errorMessage = error.message;
                  // ..
                });
              ```
        - 기존 사용자 로그인
          - 기존 사용자가 자신의 이메일 주소와 비밀번호를 사용해 로그인할 수 있는 양식을 만든다. 사용자가 양식을 작성하면 signInWithEmailAndPassword 메서드를 호출한다.
            - ```
              import { getAuth, signInWithEmailAndPassword } from "firebase/auth";

              const auth = getAuth();
              signInWithEmailAndPassword(auth, email, password)
                .then((userCredential) => {
                  // Signed in
                  const user = userCredential.user;
                  // ...
                })
                .catch((error) => {
                  const errorCode = error.code;
                  const errorMessage = error.message;
                });
              ```
        - 인증 상태 관찰자 설정 및 사용자 데이터 가져오기
          - 로그인한 사용자에 대한 정보가 필요한 앱 페이지마다 전역 인증 객체에 관찰자를 연결한다. 사용자의 로그인 상태가 변경될 때마다 이 관찰자가 호출된다.
          - onAuthStateChanged 메서드를 사용해 관찰자를 연결한다. 사용자가 로그인되면 관찰자에서 사용자에 대한 정보를 가져올 수 있다.
            - ```
              import { getAuth, onAuthStateChanged } from "firebase/auth";

              const auth = getAuth();
              onAuthStateChanged(auth, (user) => {
                if (user) {
                  // User is signed in, see docs for a list of available properties
                  // https://firebase.google.com/docs/reference/js/auth.user
                  const uid = user.uid;
                  // ...
                } else {
                  // User is signed out
                  // ...
                }
              });
              ```
      - Manage Users(Firebase에서 사용자 관리하기)
        - 사용자 생성
        - 현재 로그인한 사용자 가져오기
          - 현재 사용자를 가져올 때 권장하는 방법은 다음과 같이 Auth 객체에 관찰자를 설정하는 것이다.
            - ```
              import { getAuth, onAuthStateChanged } from "firebase/auth";

              const auth = getAuth();
              onAuthStateChanged(auth, (user) => {
                if (user) {
                  // User is signed in, see docs for a list of available properties
                  // https://firebase.google.com/docs/reference/js/auth.user
                  const uid = user.uid;
                  // ...
                } else {
                  // User is signed out
                  // ...
                }
              });
              ```
          - 관찰자를 사용하면 현재 사용자를 가져올 때 Auth 객체가 중간 단계(초기화 등)에 있지 않도록 할 수 있다. signInWithRedirect를 사용하면 onAuthStateChanged
          관찰자는 getRedirectResult가 해결될 때까지 기다린 후에 트리거된다.
          - currentUser 속성을 사용하여 현재 로그인한 사용자를 가져올 수도 있다. 사용자가 로그인 상태가 아니라면 currentUser 값이 null이다.
            - ```
              import { getAuth } from "firebase/auth";

              const auth = getAuth();
              const user = auth.currentUser;

              if (user) {
                // User is signed in, see docs for a list of available properties
                // https://firebase.google.com/docs/reference/js/auth.user
                // ...
              } else {
                // No user is signed in.
              }
              ```
        - 사용자 프로필 가져오기
          - 사용자의 프로필 정보를 가져오려면 User 인스턴스의 속성을 사용한다. 예를 들면 다음과 같다.
            - ```
              import { getAuth } from "firebase/auth";

              const auth = getAuth();
              const user = auth.currentUser;
              if (user !== null) {
                // The user object has basic properties such as display name, email, etc.
                const displayName = user.displayName;
                const email = user.email;
                const photoURL = user.photoURL;
                const emailVerified = user.emailVerified;

                // The user's ID, unique to the Firebase project. Do NOT use
                // this value to authenticate with your backend server, if
                // you have one. Use User.getToken() instead.
                const uid = user.uid;
              }
              ```
        - 제공업체별 사용자 프로필 정보 가져오기
          - 사용자에게 연결된 로그인 제공업체로부터 프로필 정보를 가져오려면 providerData 속성을 사용한다. 예를 들면 다음과 같다.
            - ```
              import { getAuth } from "firebase/auth";

              const auth = getAuth();
              const user = auth.currentUser;

              if (user !== null) {
                user.providerData.forEach((profile) => {
                  console.log("Sign-in provider: " + profile.providerId);
                  console.log(" Provider-specific UID: " + profile.uid);
                  console.log(" Name: " + profile.displayName);
                  console.log(" Email: " + profile.email);
                  console.log(" Photo URL: " + profile.photoURL);
                });
              }
              ```
        - 사용자 프로필 업데이트
          - 사용자의 표시 이름 및 프로필 사진 URL 등의 기본 프로필 정보를 업데이트할 때는 updateProfile 메서드를 사용한다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, updateProfile } from "firebase/auth";
              
              const auth = getAuth();
              updateProfile(auth.currentUser, {
                displayName: "Jane Q. User", photoURL: "https://example.com/jane-q-user/profile.jpg"
              }).then(() => {
                // Profile updated!
                // ...
              }).catch((error) => {
                // An error occurred
                // ...
              });
              ```
        - 사용자 이메일 주소 설정
          - updateEmail 메서드로 사용자의 이메일 주소를 설정할 수 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, updateEmail } from "firebase/auth";

              const auth = getAuth();
              updateEmail(auth.currenUser, "user@example.com").then(() => {
                // Email updated!
                // ...
              }).catch((error) => {
                // An error occurred
                // ...
              });
              ```
        - 사용자에게 인증 메일 보내기
          - sendEmailVerification 메서드로 사용자에게 주소 인증 메일을 보낼 수 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, sendEmailVerification } from "firebase/auth";

              const auth = getAuth();
              sendEmailVerification(auth.currentUser)
                .then(() => {
                  // Email verfication sent!
                  // ...
                });
              ```
          - 또한 Firebase Console '인증' 섹션의 '이메일 템플릿' 페이지에서 이메일 템플릿을 맞춤설정할 수 있다.
          - 인증 메일을 보낼 떄 연결 URL을 통해 상태를 전달하여 앱으로 다시 리디렉션할 수도 있다.
          - 또한 이메일을 보내기 전에 인증 인스턴스의 언어 코드를 업데이트하면 인증 메일을 현지화할 수 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth } from "firebase/auth";

              const auth = getAuth();
              auth.languageCode = 'it';
              // To apply the default browser preference instead of explicitly setting it.
              // auth.useDeviceLanguage();
              ```
        - 사용자 비밀번호 설정
          - updatePassword 메서드로 사용자의 비밀번호를 설정할 수 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, updatePassword } from "firebase/auth";

              const auth = getAuth();
              const user = auth.currentUser;
              const newPassword = getASecureRandomPassword();

              updatePassword(user, newPassword).then(() => {
                // Update successful.
              }).catch((error) => {
                // An error occurred
                // ...
              });
              ```
        - 비밀번호 재설정 이메일 보내기
          - sendPasswordResetEmail 메서드로 사용자에게 비밀번호 재설정 이메일을 보낼 수 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, sendPasswordResetEmail } from "firebase/auth";

              const auth = getAuth();
              sendPasswordResetEmail(auth, email)
                .then(() => {
                  // Password reset email sent!
                  // ..
                })
                .catch((error) => {
                  const errorCode = error.code;
                  const errorMessage = error.message;
                  // ..
                });
              ```
          - 또한 Firebase Console '인증' 섹션의 '이메일 템플릿' 페이지에서 이메일 템플릿을 맞춤설정할 수 있다.
          - 비밀번호 재설정 이메일을 보낼 때 연결 URL을 통해 상태를 전달하여 앱으로 다시 리디렉션할 수도 있다.
          - 또한 이메일을 보내기 전에 인증 인스턴스의 언어 코드를 업데이트하면 비밀번호 재설정 이메일을 현지화할 수 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth } from "firebase/auth";

              const auth = getAuth();
              auth.languageCode = 'it';
              // To apply the default browser preference instead of explicitly setting it.
              // auth.useDeviceLanguage();
              ```
          - 또한 Firebase Console에서 비밀번호 재설정 이메일을 보낼 수도 있다.
        - 사용자 삭제하기
          - delete 메서드로 사용자 계정을 삭제할 수도 있다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, deleteUser } from "firebase/auth";

              const auth = getAuth();
              const user = auth.currentUser;

              deleteUser(user).then(() => {
                // User deleted.
              }).catch((error) => {
                // An error occurred
                // ...
              });
              ```
          - 또한 Firebase Console '인증' 섹션의 '사용자' 페이지에서 사용자를 삭제할 수도 있다.
        - 사용자 재인증하기
          - 계정 삭제, 기본 이메일 주소 설정, 비밀번호 변경과 같이 보안에 민감한 작업을 하려면 사용자가 최근에 로그인한 적이 있어야 한다. 이런 작업을 할 때 사용자가 너무
          오래 전에 로그인했다면 오류가 발생하면서 작업이 실패한다. 이때에는 사용자에게 새로운 로그인 인증 정보를 받은 다음 이 정보를 reauthenticateWithCredential에
          전달하여 사용자를 재인증해야 한다. 예를 들면 다음과 같다.
            - ```
              import { getAuth, reauthenticateWithCredential } from "firebase/auth";

              const auth = getAuth();
              const user = auth.currentUser;

              // TODO(you): prompt the user re-provide their sign-in credentials
              const credential = promptForCredentials();

              reauthenticateWithCredential(user, credential).then(() => {
                // User re-authenticated.
              }). catch((error) => {
                // An error occurred
                // ...
              });
              ```
        - 사용자 계정 가져오기
          - Firebase CLI의 auth:import 명령어를 사용하여 파일에서 Firebase 프로젝트로 사용자 계정을 가져올 수 있다. 예를 들면 다음과 같다.
            - `firebase auth:import users.json --hash-algo=scrypt --rounds=8 --mem-cost=14`
      - Password Authentication
        - 시작하기 전에
          1. 자바스크립트 프로젝트에 Firebase를 추가한다.
          2. 아직 Firebase 프로젝트에 앱을 연결하지 않았다면 Firebase Console에서 연결한다.
          3. 다음과 같이 이메일 및 비밀번호 로그인을 사용 설정한다.
            - Firebase Console에서 인증 섹션을 연다.
            - 로그인 방법 탭에서 이메일/비밀번호 로그인 방법을 사용 설정하고 저장을 클릭한다.
        - 비밀번호 기반 계정 만들기
          - 비밀번호가 있는 신규 사용자 계정을 만들려면 앱의 로그인 페이지에서 다음 절차를 완료한다.
            1. 신규 사용자가 앱의 가입 양식을 사용하여 가입하면 앱에서 요구하는 새 계정 유효성 검사 단계를 완료한다. 검사 항목애는 신규 계정의 비밀번호를 정확하게 입력했는지,
            비밀번호가 복잡성 조건을 충족하는지 등이 있다.
            2. 다음과 같이 신규 사용자의 이메일 주소와 비밀번호를 createUserWithEmailAndPassword에 전달하여 신규 계정을 생성한다.
              - ```
                import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

                const auth = getAuth();
                createUserWithEmailAndPassword(auth, email, password)
                  .then((userCredential) => {
                    // Signed in
                    const user = userCredential.user;
                    // ...
                  })
                  .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                    // ..
                  });
                ```
              - 신규 계정 생성에 성공하면 사용자가 자동으로 로그인된다.
        - 이메일 주소와 비밀번호로 사용자 로그인
          - 비밀번호로 사용자 로그인을 처리하는 절차는 신규 계정을 생성하는 절차와 비슷하다. 앱의 로그인 페이지에서 다음 절차를 따르도록
            - 사용자가 앱에 로그인하면 다음과 같이 사용자의 이메일 주소와 비밀번호를 signInWithEmailAndPassword에 전달한다.
              - ```
                import { getAuth, signInWithEmailAndPassword } from "firebase/auth";

                const auth = getAuth();
                signInWithEmailAndPassword(auth, email, password)
                  .then((userCredential) => {
                    // Signed in
                    const user = userCredential.user;
                    // ...
                  })
                  .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                  })
                ```
      - Email Link Authentication(이메일 링크를 사용하여 자바스크립트에서 Firebase 인증)
        - Firebase 프로젝트에서 이메일 링크 로그인 사용 설정
          1. Firebase Console에서 인증 섹션을 연다.
          2. 로그인 방법 탭에서 이메일/비밀번호 제공업체를 사용 설정한다. 이메일 링크 로그인을 사용하려면 이메일/비밀번호를 로그인이 사용 설정되어야 한다.
          3. 같은 섹션에서 이메일 링크(비밀번호가 없는 로그인) 로그인을 사용 설정한다.
          4. 저장을 클릭한다.
        - 사용자의 이메일 주소로 인증 링크 전송
          - 이 인증 과정을 시작하려면 사용자에게 이메일 주소를 제공하도록 요청하는 인터페이스를 제시하고 sendSignInLinkToEmail을 호출하여 Firebase가 사용자의
          이메일에 인증 링크를 전송하도록 요청한다.
            1. Firebase에 이메일 링크를 만드는 방법에 대한 지침을 제시하는 ActionCodeSettings 객체를 만든다. 다음 필드를 설정한다.
              - url: 삽입할 딥 링크 및 함께 전달할 추가 상태이다. 승인된 도메인의 Firebase Console 목록에 링크의 도메인을 추가해야 하며 로그인 방법 탭
              (인증 -> 로그인 방법)으로 이동하여 확인할 수 있다.
              - android 및 ios: Android 또는 Apple 기기에서 로그인 링크를 열 때 사용하는 앱이다. 모바일 앱을 통해 이메일 작업 링크를 열기 위해 Firebase 동적
              링크를 구성하는 방법에 대해 자세히 알아보도록.
              - handleCodeInApp: true로 설정한다. 다른 대역 외 이메일 작업(비밀번호 재설정 및 이메일 인증)과 달리 이 로그인 작업은 항상 앱에서 완료해야 한다. 그
              이유는 인증 과정 마지막에 사용자가 로그인하고 사용자의 인증 상태를 앱에서 유지해야 하기 때문이다.
              - dynamicLinkDomain: 프로젝트에 여러 개의 커스텀 동적 링크 도메인이 정의된 경우 지정된 모바일 앱을 통해 링크를 열 때 사용할 도메인을 지정한다.
              (예: example.page.link). 지정하지 않으면 첫 번째 도메인이 자동으로 선택된다.
                - ```
                  const actionCodeSettings = {
                    // URL you want to redirect back to. The domain (www.example.com) for this
                    // URL must be in the authorized domains list in the Firebase console.
                    url: 'https://www.example.com/finishSignUp?cartId=1234',
                    // This must be true.
                    handleCodeInApp: true,
                    iOS: {
                      bundleId: 'com.example.ios'
                    },
                    android: {
                      packageName: 'com.example.android',
                      installApp: true,
                      minimumVersion: '12',
                    },
                    dynamicLinkDomain: 'example.page.link'
                  };
                  ```
              - ActionCodeSettings에 대해 자세히 알아보려면 이메일 작업의 상태 전달 섹션을 참고
            2. 사용자에세 이메일 주소 입력을 요청한다.
            3. 사용자의 이메일에 인증 링크를 전송하고 사용자가 같은 기기에서 이메일 로그인을 완료할 경우에 대비해 사용자의 이메일을 저장한다.
              - ```
                import { getAuth, sendSignInLinkToEmail } from "firebase/auth";

                const auth = getAuth();
                sendSignInLinkToEmail(auth, email, actionCodeSettings)
                  .then(() => {
                    // The link was successfully sent. Inform the user.
                    // Save the email locally so you don't need to ask the user for it again
                    // if they open the link on the same device.
                    window.localStorage.setItem('emailForSignIn', email);
                    // ...
                  })
                  .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                    // ...
                  });
                ```
          - 이메일 링크로 로그인 완료
      - Google
      - Facebook Login
  - Cloud Firestore
    - Introduction
    - Get started
      - Cloud Firestore 데이터베이스 만들기
        1. Firebase 프로젝트를 아직 만들지 않았다면 Firebase Console에서 프로젝트 추가를 클릭한 후 화면의 안내에 따라 Firebase 프로젝트를 만들거나 기존
        GCP 프로젝트에 Firebase 서비스를 추가한다.
        2. 앱의 Cloud Firestore 섹션으로 이동한다. Firebase Console 기존 Firebase 프로젝트를 선택하라는 메시지가 표시된다. 데이터베이스 만들기 워크플로를 따른다.
        3. Cloud Firestore Security Rules의 시작 모드 선택:
          - 테스트 모드
            - 모바일 및 웹 클라이언트 라이브러리를 시작할 때 유용하지만 모든 사용자가 데이터를 읽고 덮어쓸 수 있다. 테스트 완료 후 데이터 보안 섹션을 검토해야 한다.
            - 웹, Apple 플랫폼 또는 Android SDK를 시작하려면 테스트 모드를 선택할 것.
          - 잠금 모드
            - 모바일 및 웹 클라이언트의 모든 읽기 및 쓰기를 거부한다. 인증된 애플리케이션 서버 (C#, Go, 자바, Node.js, PHP, Python, Ruby)에서는 사용자의 데이터베이스에 계속 액세스할 수 있다.
            - C#, Go, 자바, Node.js, PHP, Python 또는 Ruby 서버 클라이언트 라이브러리를 시작하려면 잠금 모드를 선택할 것
        4. 데이터베이스의 위치를 선택한다.
          - 이 위치 설정이 프로젝트의 기본 Google Cloud Platform(GCP) 리소스 위치이다. 이 위치는 프로젝트의 GCP 서비스에 사용된다. 위치 설정이 필요한 캠페인,
          특히 위치 설정이 필요한 캠페인, 특히 기본 Cloud Storage 버킷 및 App Engine 앱 (즉, 필수)이다.
          - 위치를 선택할 수 없다면 프로젝트에 이미 기본 GCP 리소스 위치가 있는 것이다. 이 위치는 프로젝트 생성 과정이나 위치 설정이 필요한 다른 서비스를 설정할 떄 지정한 것이다.
        5. 완료를 클릭한다.
      - 개발 환경 설정
        - Web modular API
          ```
          1. 안내에 따라 Firebase를 웹 앱에 추가한다.
          2. Cloud Firestore SDK는 npm 패키지로 제공된다.
            npm install firebase@10.13.1 --save
             드림 Firebase와 Cloud Firestore를 모두 가져와야 한다.
            import { initializeApp } from "firebase/app";
            import { getFirestore } from "firebase/firestore";
          ```
        - iOS+
          - 안내에 따라 Firebase를 Apple 앱에 추가한다.
          - Swift Package Manager를 사용해 Firebase 종속 항목을 설치하고 관리할 것
            1. 앱 프로젝트를 연 상태로 Xcode에서 File(파일) > Swift Packages(Swift 패키지) > Add Package Dependency(패키지 종속 항목 추가)로 이동한다.
            2. 메시지가 표시되면 Firebase Apple 플랫폼 SDK 저장소를 추가한다.
              `https://github.com/firebase/firebase-ios-sdk`
               드림 <ph type="x-smartling-placeholder">
            3. Firestore 라이브러리를 선택한다.
            4. 완료되면 Xcode가 백그라운드에서 자동으로 종속 항목을 확인하고 다운로드하기 시작한다.
        - Android
          ```
          1. 안내에 따라 Firebase를 Android 앱에 추가한다.
          2. Firebase Android BoM Android용 Cloud Firestore 라이브러리의 종속 항목을 모듈 (앱 수준) Gradle 파일 (일반적으로 app/build.gradle.kts 또는
          app/build.gradle)을 입력한다.
            dependencies {
              // Import the BoM for the Firebase platform
              implementation(platform("com.google.firebase:firebase-bom:33.2.0"))

              // Declare the dependency for the Cloud Firestore library
              // When using the BoM, you don't specify versions in Firebase library dependencies
              implementation("com.google.firebase:firebase-firestore")
            }
          ```
      - (선택사항) Firebase Local Emulator Suite로 프로토타입 제작 및 테스트
      - Cloud Firestore 초기화
        - Web
          ```
          import { initializeApp } from "firebase/app";
          import { getFirestore } from "firebase/firestore";

          // TODO: Replace the following with your app's Firebase project configuration
          // See: https://support.google.com/firebase/answer/7015592
          const firebaseConfig = {
            FIREBASE_CONFIGURATION
          };

          // Initialize Firebase
          const app = initializeApp(firebaseConfig);

          // Initialize Cloud Firestore and get a reference to the service
          const db = getFirestore(app);
          ```
          - FIREBASE_CONFIGURATION을 웹 앱의 firebaseConfig로 바꾼다.
        - Swift
          ```
          import FirebaseCore
          import FirebaseFirestore

          FirebaseApp.configure()
          let db = Firestore.firestore()
          ```
        - Kotlin
          ```
          // Access a Cloud Firestore instance from your Activity

          val db = Firebase.firestore
          ```
      - 데이터 추가
        - Cloud Firestore는 컬렉션에 저장되는 문서에 데이터를 저장한다. Cloud Firestore가 암시적으로 컬렉션 및 문서 만들기 할 수 있다. 컬렉션이나 문서를 명시적으로
        만들 필요가 없다.
        - 다음 예시 코드를 사용해 새 컬렉션과 문서를 만든다.
          - Web
            ```
            import { collection, addDoc } from "firebase/firestore";

            try {
              const docRef = await addDoc(collection(db, "users"), {
                first: "Ada",
                last: "Lovelace",
                born: 1815
              });
              console.log("Document written with ID: ", docRef.id);
            } catch (e) {
              console.error("Error adding document: ", e);
            }
            ```
          - Swift
            ```
            // Add a new document with a generated ID
            do {
              let ref = try awaid db.collection("users").addDocument(data: [
                "first": "Ada",
                "last": "Lovelace",
                "born": 1815
              ])
              print("Document added with ID: \(ref.documentID)")
            } catch {
              print("Error adding document: \(error)")
            }
            ```
          - Kotlin
            ```
            // Create a new user with a first and last name
            val user = hashMapOf(
              "first" to "Ada",
              "last" to "Lovelace",
              "born" to 1815
            )

            // Add a new document with a generated ID
            db.collection("users")
              .add(user)
              .addOnSuccessListener { documentReference ->
                Log.d(TAG, "DocumentSnapshot added with ID: ${documentReference.id}")
              }
              .addOnFailureListener { e ->
                Log.w(TAG, "Error adding documnet", e)
              }
            ```   
        - 이제 users 컬렉션에 다른 문서를 추가한다. 첫 번째 문서에는 나타나지 않는 키-값 쌍(중간 이름)이 문서에 포함된다는 점에 유의하라. 컬렉션의 문서에는 다른 정보
        집합이 포함될 수 있다.
          - Web
            ```
            // Add a second document with a generated ID.
            import { addDoc, collection } from "firebase/firestore";

            try {
              const docRef = await addDoc(collection(db, "users"), {
                first: "Alan",
                middle: "Mathison",
                last: "Turing",
                born: 1912
              });
              console.log("Document written with ID: ", docRef.id);
            } catch (e) {
              console.error("Error adding document: ", e)
            }
            ```
          - Swift
            ```
            // Add a second document with a generate ID.
            do {
              let ref = try await db.collection("users").addDocument(data: [
                "first": "Alan",
                "middle": "Mathison",
                "last": "Turing",
                "born": 1912
              ])
              print("Document added with ID: \(ref.documentID)")
            } catch {
              print("Error adding document: \(error)")
            }
            ```
          - Kotlin
            ```
            // Create a new user with a first, middle, and last name
            val user = hashMapOf(
                "first" to "Alan",
                "middle" to "Mathison",
                "last" to "Turing",
                "born" to 1912,
            )

            // Add a new document with a generated ID
            db.collection("users")
                .add(user)
                .addOnSuccessListener { documentReference ->
                    Log.d(TAG, "DocumentSnapshot added with ID: ${documentReference.id}")
                }
                .addOnFailureListener { e ->
                    Log.w(TAG, "Error adding document", e)
                }
            ```
      - 데이터 읽기
        - 데이터 사용 뷰어 Firebase Console에서 Cloud Firestore에 데이터를 추가했는지 빠르게 확인할 수 있다.
        - 'get'메서드를 사용해 전체 컬렉션을 가져올 수도 있다.
        - Web
          ```
          import { collection, getDocs } from "firebase/firestore"

          const querySnapshot = await getDocs(collection(db, "users"));
          querySnapshot.forEach((doc) => {
            console.log(`${doc.id} => ${doc.data()}`);
          });
          ```
        - Swift
          ```
          do {
            let snapshot = try await db.collection("users").getDocuments()
            for document in snapshot.documents {
              print("\(document.documentID) => \(documet.data())")
            }
          } catch {
            print("Error getting documents: \(error)")
          }
          ```
        - Kotlin
          ```
          db.collection("users")
            .get()
            .addOnSuccessListener { result ->
              for (document in result) {
                Log.d(TAG, "${document.id} => ${document.data}")
              }
            }
            .addOnFailureListener { exception ->
              Log.w(TAG, "Error getting document.", exception)
            }
          ```
      - 데이터 보안
        - 웹, Android 또는 Apple 플랫폼 SDK를 사용하는 경우 Firebase 인증 밑 Cloud Firestore Security Rules를 사용해 데이터를 안전하게 보호하세요
        - 다음은 시작하는 데 사용할 수 있는 기본 규칙 세트이다. Console의 규칙 탭에서 보안 규칙을 수정할 수 있다.
          - 인증 필요
            ```
            // Allow read/write access to a document keyed by the user's UID
            service cloud.firestore {
              match /databases/{database}/documments {
                match /users/{uid} {
                  allow read, writeL if request.auth != null && request.auth.uid == uid;
                }
              }
            }
            ```
    - Understand Cloud Firestore
    - Manage databases
    - Add and manage data
    - Read data
  - Storage
    - Introduction
    - iOS+
    - Android
    - Web
      - Get started
        - 기본요건
          - 아직 진행하지 않았다면 Firebase JS SDK를 설치하고 Firebase를 초기화한다.
        - 기본 Cloud Storage 버킷 만들기
          1. Firebase 콘솔의 탐색창에서 Storage를 선택한다. 시작하기를 클릭한다.
          2. 보안을 사용하여 Cloud Storage 데이터를 보호하는 방법에 관한 메시지 검토 있다. 개발 중에는 공개 액세스 규칙 설정
          3. 기본 위치를 선택한다. Cloud Storage 버킷
            - 이 위치 설정이 
        - 공개 액세스 설정
        - 앱에 버킷 URL 추가
        - 고급 설정
      - Create a Reference
      - Upload Files
      - Download Files
      - Use File Metadata
      - Delete Files
      - List Files
      - Handle Errors

## Cloud
### GitHub Pages
- 빠른 시작
- 시작하기
  - GitHub Pages 정보
  - GitHub Pages 사이트 만들기
  - 워크플로 사용자 지정 사용
  - 게시 원본 구성
  - GitHub pages 사이트 삭제
  - Pages 사이트 게시 취소
  - 사용자 지정 404 페이지 만들기
  - HTTPS로 사이트 보호
  - 페이지에 하위 모듈 사용
  - 404 오류 해결
- Jekyll을 사용하여 사이트 설정
- 사용자 지정 도메인 구성 

### vercel
- Documentation
  - Platform
    - Get Started
      - Step 1: Projects & Deployments
        - Option 1: Use a Template
        - Option 2: Import an Existing Project
      - Step 2: Add a Domain
        - Option 1: Buy a domain
        - Option 2: Transfer an existing domain
      - Step 3: Collaborate
    - Frameworks
      - Next.js
      - Create React App
        - Get Started with CRA on Vercel
        - Static file caching
          - vercel에서 정적 파일은 첫 번째 요청 후 글로벌 Edge Network의 모든 지역에 복제되고 배포된다. 이를 통해 정적 파일이 방문자에게 가장 가까운
          위치에서 제공되어 성능이 향상되고 지연 시간이 줄어든다.
          - 정적 파일은 최대 31일 동안 캐시된다. 파일이 변경되지 않은 경우 해시가 정적 파일을 캐시하므로 배포 전체에 걸쳐 지속될 수 있다. 그러나
          재배포하면 캐시가 효과적으로 무효화되므로 항상 최신 버전을 제공한다.
          - 요약하자면 Vercel에서 CRA와 함께 정적 파일을 사용하는 방법은 다음과 같다.
            - 최상의 성능을 위해 자산을 자동으로 최적화하고 캐시한다.
            - public 폴더를 통해 파일에 쉽게 접근할 수 있다.
            - 다운타임 없는 롤아웃 지원
            - 구매 또는 설정에 추가 서비스가 필요하지 않다.
        - Preview Deployments
        - Edge Functions
        - Web Analytics
        - Speed insights
        - Observability
      - Vite
    - Projects    
      - Managing Projects
        - Create a project
        - pausing a project
        - Deleting a project
      - Transferring a Project
      - Monorepos
        - Turborepo
      - Environment Variables
      - Project Dashboard
    - Builds
    - Deployments
    - Domains
  - Infrastructure
  - Workflow
  - Storage
- Guides

### netlify

### amplify

<hr />
