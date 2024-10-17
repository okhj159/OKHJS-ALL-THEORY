# Mobile Applications

## 목차
1. [개요](#개요)
2. [hybrid app](#hybrid-app)
3. [native app](#native-app)
4. [web app](#web-app)

## 개요
- 

## hybrid app
- 네이티브 앱과 웹 앱의 장점을 결합한 앱

### React Native
- Guides
    - The Basics
        - Core Components and Native Components
            - Native Components
                - React Native 구성 요소는 Android 및 iOS와 동일한 보기로 지원되므로 React Native 앱은 다른 앱과 마찬가지로
                  모양, 느낌, 성능이 동일하다. 이러한 플랫 폼 지원 구성 요소를 Native Components라고 부른다.
            - Core Components
                - React Native는 컨트롤부터 활동 지시자까지 모든 것을 위한 Core Components들을 가지고 있다.
                - 다음과 같은 Core Components들을 사용할 것이다.<br>
                  <img src="react_native/core_components.png">
        - React Fundamentals
            - State
                - props는 component를 렌더링 방법을 구성하는데 사용되는 인수인 반면에, state는 컴포넌트의 개인적인 데이터 스토리지이다.
                - state는 시간이 지남에 따라 변경되거나 사용자 상호작용을 통해 발생하는 데이터를 처리하는데 유용하다.
        - Using List Views
            - React Native는 data의 리스트를 표현하기 위해 적합한 component를 제공한다. 일반적으로 FlatList나 SectionList
              중에서 사용할 수 있다.
            - FlatList component는 데이터의 변화의 scrolling list를 보여준다.
            - FlatList component는 data와 renderItem이라는 2가지 props를 필요로 한다.
                - data는 리스트의 정보의 소스이다.
                - renderItem은 소스로부터 하나의 항목을 가져와 렌더링할 형식이 지정된 구성 요소를 반환한다.
    - Environment setup
        - Setting up the development
            - macOS
                - iOS
                    - Installing dependencies
                        - Node, Watchman, React Native CLI, Xcode and cocoaPods가 필요하다.
                        - Node & Watchman
                            ```
                                brew install node
                                brew install watchman
                            ```
                            - Watchman은 페이스북에서 개발한 파일시스템 변경을 확인하는 강력한 툴이다.
                        - Xcode
                            - Xcode를 설치하는 가장 쉬운 방법은 앱 스토어를 이용하는 것이다.
                            - CocoaPods
                                - iOS에서 사용할 수 있는 종속성 관리 시스템중 하나이다. CocoaPods는 Ruby gem이다. 최신 macOS 버전에 
                                  동봉된 Ruby 버전을 이용하여 설치할 수 있다.
                        - React Native CLI
                            - React Native는 CLI가 내장되어 있다. 특정 버전을 전역적으로 설치하고 관리하는 것보다는 Node.js에 내장된 npx
                              의 런타임의 현재 버전에 접근하는 것이 좋다. npx react-native '<command>'를 이용하면 현재 안정적인 CLI 버전이
                              다운되고 실행된다.
                - Android
                    - Installing dependencies
                        - Node, Watchman, React Native CLI, JDK, Android Studio가 필요하다.
                        - Node & Watchman
                            ```
                                brew install node
                                brew install watchman
                            ```
                            - Watchman은 페이스북에서 개발한 파일시스템 변경을 확인하는 강력한 툴이다.
    - UI & Interaction
        - style
            - 모든 core components는 style이라는 prop을 채택한다. style은 CSS가 웹에서 작동하는 것과
              camel case로 작성되는 것 빼고는 거의 매칭된다.
        - Height and Width
            - Fixed Dimensions
                - 컴포넌트의 차원을 세팅하는 일반적인 방법은 width와 height를 고정하여 style에 더하는 것이다.
            - Flex Dimensions
                - 사용 가능한 공간에 따라 컴포넌트를 동적으로 확장이나 축소를 하려면 컴포넌트 스타일에 flex를 사용하면 된다.
                - 일반적으로 flex: 1을 사용하게 될 것인데, 이는 컴포넌트가 사용가능한 공간을 채우게 지시한다. 또한, 동일한
                  부모 컴포넌트를 가진 다른 컴포넌트 사이에서 공유가능하게 한다.
                - 주어진 flex가 클수록 형제에 비해 공간을 차지하는 비율이 커지게 된다.
            - Percent Dimensions
        - Layout with Flexbox
            - Flex
                - flex는 main 축을 따라 사용 가능한 공간을 따라 어떻게 채울 것인지 정의한다.
            - Flex Direction
                - flexDirection은 노드의 자식이 배치되는 방향을 지시한다.
            - Justify Content
                - flex-start(default value)
                - flex-end
                - center
                - space-between
                - space-around
                - space-evenly
            - Align Items
                - alignItems는 교차축에 따라 자식들을 정렬하는 것을 지시한다. justifyContents와 유사하지만 주축에 적용하는 대신
                  교차축에 적용된다.
                - stretch(default value)
                - flex-start
                - flex-end
                - center
                - baseline
        - Interaction
            - Navigating Between Screens
                - React Navigation
                    - Installation and setup
                        - 먼저, 프로젝트에 다음과 같이 인스톨한다.
                          ``` 
                            $ npm install @react-navigation/native @react-navigation/native-stack
                          ```
                        - 다음으로, 피어 종속성을 설치한다.
                          ```
                            $ npm install react-native-screens react-native-safe-area-context
                          
                            react-native 프로젝트에 CocoaPods가 설치되어 있는지 확인하고 다음 명령어를 실핸한다.
                            $ cd ios
                            $ pod install
                            $ cd ..
                          ```
                        - 이제, 전체 app을 NavigationContainer으로 감쌀 필요가 있다. 종종 엔트리 파일인 index.js나 App.js에
                          작업을 할 것이다.
                          ```
                            import * as React from 'react';
                            import {NavigationContainer} from '@react-navigation/native';
                            
                            const App = () => {
                               return (
                                  <NavigationContainer>
                                     {/* Rest of your app code */}
                                  </NavigationContainer>
                               );
                            };
                            
                            export default App;
                          ```
                    - Usage
                        - 이제, 다음과 같이 home screen과 profile screen을 만들 수 있다.
                          ```
                            import * as React from 'react';
                            import {NavigationContainer} from '@react-navigation/native';
                            import {createNativeStackNavigator} from '@react-navigation/native-stack';
                            
                            const Stack = createNativeStackNavigator();
                            
                            const MyStack = () => {
                               return (
                                  <NavigationContainer>
                                     <Stack.Navigator>
                                        <Stack.Screen
                                           name="Home"
                                           component={HomeScreen}
                                           options={{title: 'Welcome'}}
                                        />
                                        <Stack.Screen name="Profile" component={ProfileScreen} />
                                     </Stack.Navigator>
                                  </NavigationContainer>
                               );
                            };
                          ```
        - Networking
            - Using Fetch
                - Making requests
                - Handling the response
            - Using Other Networking Libraries
            - WebSocket Support
    - Debugging
    - Testing
    - Native Modules
        - Native Modules Intro
        - Android Native Modules
        - iOS Native Modules
        - Native Modules NPM Package Setup
        - Loval libraries setup
    - Native Components
        - Android Native UI Components
        - iOS Native UI Components
        - Direct Manipulation
    - Android and iOS guides
        - Android
            - Headless JS
            - Publishing to Google play Store
            - Communication between native and React Native
            - React Native Gradle Plugin
        - iOS
            - Linking Libraries
            - Running On Simulator
            - Communication between native and React Native
            - App Extensions
            - Publishing to Apple App Store
                - 배포 프로세스는 다른 native iOS app과 동일하며, 몇 가지 추가 요소가 있다.
                    1. Configure release scheme
                        - App store에 배포할 앱을 구축하려면 Xcode에 있는 Release scheme을 사용해야 한다.
                        - Release scheme을 사용하여 앱을 구성하려면, Product -> Scheme -> Edit Scheme으로 이동하라. 사이드 바에 있는 Run 탭을 선택하라, 그리고 Build Configuration 드롭다운을 하여 Release를 선택하라.
                    2. Build app for release
- Components
    - Core Components
        - Core Components and APIs
            - Basic Components
                - View
                - Text
                - Image
                - TextInput
                - ScrollView
                - StyleSheet
            - User Interface
                - Button
                - Switch
            - List Views
                - FlatList
                - SectionList
            - Android-specific
                - BackHandler
                - DrawerLayoutAndroid
                - PermissionsAndroid
                - ToastAndroid
            - iOS-specific
                - ActionSheetIOS
            - Others
        - ActivityIndicator
            - 원형 로딩 표시기를 보여준다.
        - Button
        - FlatList
            - 가장 편리한 기능을 지원하는, 기본적이고 단순한 목록을 렌더링하기 위한, 효과적인 인터페이스 이다.
        - Image
            - 네트워크 이미지, 동적 리소스, 임시 로컬 이미지, 로컬디스크의 이미지, 카메라 롤 등을 포함하는
              다른 타입의 이미지를 보여주기 위한 React 컴포넌트이다.
        - KeyboardAvoidingView
            - 이 컴포넌트는 가상 키보드가 표시되는 동안 계속 보이도록 키보드의 높이를 기준으로 하여 자동적으로 높이, 위치,
              하단 padding을 조정한다.
        - Modal
            - modal 컴포넌트는 둘러쌓인 view 위로 컨텐츠를 보여줄 수 있는 기본적인 방법이다.
        - Pressable
            - 정의된 children의 press 상호작용을 다양한 단계로 탐지할 수 있는 코어 컴포넌트 wrapper이다.
        - StatusBar
            - 앱의 상태 표시줄을 제어하는 컴포넌트 이다.
    - Android Components
    - iOS Components
- APIs
    - APIs
        - Alert
        - Appearance
        - Keyboard
        - Linking
        - StyleSheet
        - Vibration
    - Hooks
    - Android APIs
    - iOS APIs
- Architecture
    - Architecture
    - Rendering
    - Build Tools
- 기타
    - Component
        - 유저 인터페이스를 구성하는 요소
        - 컴포넌트 생성
            - ```
              const App = () => { 
                return (
                  <SafeAreaView>
                  </SafeAreaView>
              )} 
              ```
            - Props(Properties)를 설정하여 컴포넌트에 전달할 수 있다.
            - JSX 문법
                - 태그를 열면 반드시 닫아주기 `<Text></Text>`
                - 스스로 닫는 태그 사용하기   `<Text />`
                - 반환할 때 반드시 하나의 태그로 감싸기
                - JSX 안에서 자바스크립트 표현식을 보여줄 땐 중괄호 사용
    - react-native component
        - SafeAreaView
            - iPhone X 이상 기종에서 디스플레이의 보이지 않는 영역 및 최하단 영역에 내용이 보여지는 것을
              방지해준다.
        - View
            - 가장 기본적인 컴포넌트로 레이아웃 및 스타일을 담당한다.
        - Text
            - 텍스트를 보여주는 역할을 한다.
        - TextInput
            - 키보드 입력을 받아낼 때 사용하는 컴포넌트
            - iOS는 화면의 하단 부분이 키보드에 가려지는 반면, 안드로이드는 화면이 줄어든다.
        - KeyboardAvoidingView
            - 텍스트를 입력할 때 키보드가 화면을 가리지 않게 하기 위해 사용하는 컴포넌트
        - StyleSheet
            - 스타일링 컴포넌트
            - 모든 스타일 속성은 camelCase로 작성해야 한다.
        - StatusBar
            - 화면 최상단 상태 영역
            - iOS는 색상을 바꾸려면 View로 색상을 채워야 한다.
            - 안드로이드는 색상을 StatusBar 컴포넌트의 backgroundColor 속성을 이용할 수 있다.
        - TouchableOpacity
            - 터치했을 때 투명도를 조정한다.
    - Hooks
        - useState
            - 상태 값을 관리하는 함수
            - `const [visible, setVisible] = useState(true)`
    - Context API
        - 컴포넌트 사이에 공유되는 데이터를 위해 매번 공통 부모 컴포넌트를 수정하고 모든 컴포넌트에
          Props를 전달하여 데이터를 사용하는 과정은 비효율적이다. 이처럼 비효율적인 문제를 해결하기 위해
          리액트에서는 Flux라는 개념을 도입하였고, 그에 걸맞은 Context API를 제공하기 시작했다.
        - Context는 부모 컴포넌트로부터 자식 컴포넌트로 전달되는 데이터의 흐름과는 상관없이, 전역적으로
          사용되는 데이터를 다룬다.
        - Context를 사용하기 위해서는 Context Api를 사용하여 Context의 프로바이더(Provider)와
          컨슈머(Consumer)를 생성한다.
        - Context에 저장된 데이터를 사용하기 위해서는 공통 부모 컴포넌트에 Context의 프로바이더를 사용하여
          데이터를 제공하다. 그리고 데이터를 사용하려는 컴포넌트에서 Context의 컨슈머를 사용하여 실제
          데이터를 사용(소비)한다.
    - AsyncStorage
        - AsyncStorage는 리액트 네이티브에서 사용할 수 있는 key-value 형식의 저장소이다.
        - AsyncStorage는 앱 내에서 간단하게 데이터를 저장할 수 있는 저장소이다.
        - iOS에서는 네이티브 코드로 구현되어 있으며, 안드로이드에서는 네이티브 코드와 SQLite를 기반으로
          구현되어 있다.
        - 리액트에서 데이터를 다루는 Props와 State, Context는 휘발성이다. 이 데이터는 메모리에서만 존재하며,
          물리적으로 데이터를 저장하지 않는다. 따라서 데이터들은 API를 통해 서버에 저장하여 사용하거나, 앱 내에
          저장하여 사용하는 경우가 많다.
        - 웹에서 사용하는 windows.localStorage와 매우 유사하다.
        - AsyncStorage는 키 값 저장소로서 간단하게 앱 내에 데이터를 저장하기 위해 사용할 수 있다.
        - 설치하기</br>
          `$ yarn add @react-native-community/async-storage`
            - iOS에서는 다시 pod install 해줘야 한다.</br>
              ```
                 $ cd ios
                 $ pod install
              ```
    - react-navigation
        - 여러 화면으로 구성된 애플리케이션을 만드려면 내비게이션 관련 서드 파티 라이브러리를 사용해야 한다.
        - 설치법</br>
          `$ yarn add @react-navigation/native`
            - 의존 라이브러리 설치</br>
              ` yarn add react-native-screens react-native-safe-area-context`
        - 다양한 내비게이터
            - Drawer Navigator
                - 좌측 혹은 우측에 사이드바를 만들고 싶을 때 사용하는 내비게이터이다.
                - 사이드바를 모바일 앱에서는 드로어라고 부른다.
                - 설치</br>
                  `$ yarn install @react-navigation/drawer react-native-gesture-handler react-native-reanimated`
                - navigation.push, navigation.pop 같은 기능들은 드로어 내비게이터에서 호환되지 않는다.
            - Bottom Tab Navigator
                - 하단에 탭을 보여주는 내비게이터이다.
                    - 설치</br>
                      `$ yarn add @react-navigation/bottom-tabs react-native-vector-icons`
            - Material Top Tab Navigator
                - 탭을 상단에 위치시킬 수 있다.
                - 탭을 누르면 구글의 머티리얼 디자인 특유의 물결(ripple) 효과가 나타난다.
                - 화면을 스와이프하는 형태로 우측/좌측 탭으로 전환할 수도 있다.
                - 설치</br>
                  `$ yarn add @react-navigation/material-top-tabs react-native-tab-view react-native-paper-view`
            - Material Bottom Tab Navigator
                - 설치</br>
                  `$ yarn add @react-navigation/material-bottom-tabs react-native-paper`
        - 내비게이션 Hooks
            - useNavigation
                - 이 Hook을 사용하면 Screen으로 사용되고 있지 않은 컴포넌트에서도 navigation 객체를 사용할 수 있다.
                - useNavigation을 사용하면 navigation을 상위 컴포넌트에서 Props로 넣어주지 않아도 사용할 수 있다.
            - useRoute
                - useRoute는 useNavigation과 비슷하게, Screen이 아닌 컴포넌트에서 route 객체를 사용할 수 있게 한다.
            - useFocusEffect
                - 화면에 포커스가 잡혔을 때 특정 작업을 할 수 있게 하는 Hook이다.

### React Native Library

#### React Navagation
- Fundamentals
    - Hello React Navagation
        - 웹 브라우저에서 앵커(`<a>`) 태그를 사용하여 다른 페이지에 링크할 수 있다. 사용자가 링크를 클릭하면 URL이 브라우저 기록 스택에 푸시된다. 사용자가 뒤로 가기 버튼을
          누르면 브라우저가 기록 스택 맨 위에서 항목을 팝 하므로 활성 페이지는 이제 이전에 방문한 페이지가 된다. React Native에서 웹 브라우저와 같은 글로벌 기록 스택에 대한
          기본 제공 아이디어가 없다. 여기서 React Navigation이 스토리에 등장한다.
        - React Navigation의 네이티브 스택 네비게이터는 앱이 화면 간에 전환하고 탐색 기록을 관리할 수 있는 방법을 제공한다. 앱에서 스택 네비게이터를 하나만 사용하는 경우
          웹 브라우저가 탐색 상태를 처리하는 방식과 개념적으로 비슷하다. 즉, 앱은 사용자가 탐색 스택과 상호 작용할 때 탐색 스택에서 항목을 푸시하고 팝하며, 그 결과 사용자는
          다른 화면을 보게 된다. 이것이 웹 브라우저와 React Navigation에서 작동하는 방식의 주요 차이점은 React Navagation의 네이티브 스택 네비게이터가 스택의 경로 간에
          탐색할 때 Android와 iOS에서 기대하는 제스처와 애니메이션을 제공한다는 것이다.
        - 가장 일반적인 네비게이터인 createNativeStackNavigator부터 설명하도록 하겠다.
        - Creating a native stack navigator 
            - createNativeStackNavigator는 2가지 속성(Screen과 Navigator)를 포함하는 객체를 반환하는 함수이다. 둘 다 네비게이터 구성요소에 사용되는 React
              component이다. Navigator는 경로 구성을 정의하기 위해 Screen 원소를 하위 요소로 반드시 포함해야 한다.
            - NavigationContainer는 navigation tree를 관리하고 navigation state를 포함하는 component이다. 이 컴포넌트는 모든 navigator 구조를 감싸야만 한다.
              일반적으로 App.js에서 내보낸 컴포넌트인 앱의 최상단에 이 컴포넌트를 렌더링한다.
            - 
              ```
                // In App.js in a new project

                import * as React from 'react';
                import { View, Text } from 'react-native';
                import { NavigationContainer } from '@react-navigation/native';
                import { createNativeStackNavigator } from '@react-navigation/native-stack';

                function HomeScreen() {
                  return (
                    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
                      <Text>Home Screen</Text>
                    </View>
                  );
                }

                const Stack = createNativeStackNavigator();

                function App() {
                  return (
                    <NavigationContainer>
                      <Stack.Navigator>
                        <Stack.Screen name="Home" component={HomeScreen} />
                      </Stack.Navigator>
                    </NavigationContainer>
                  );
                }

                export default App;
              
              ```
        - Configuring the navigator
            - 모든 경로 구성은 navigator의 props로 지정된다. 
            - native stack navigator에 2번째 screen을 추가하고, Home screen을 처음에 렌더링하도록 구성해보자.
              ```
                function DetailsScreen() {
                  return (
                    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
                      <Text>Details Screen</Text>
                    </View>
                  );
                }

                const Stack = createNativeStackNavigator();

                function App() {
                  return (
                    <NavigationContainer>
                      <Stack.Navigator initialRouteName="Home">
                        <Stack.Screen name="Home" component={HomeScreen} />
                        <Stack.Screen name="Details" component={DetailsScreen} />
                      </Stack.Navigator>
                    </NavigationContainer>
                  );
                }
              ```
            - 이제, stack에는 Home과 Details 2가지 경로를 가지게 되었다. 경로는 Screen 컴포넌트를 사용함으로써 지정되어진다. Screen 컴포넌트는 탐색에 사용될 경로의 이름에
              해당하는 name props와 렌더링될 컴포넌트에 해당하는 component props를 가진다.
            - Home 경로에 해당하는 HomeScreen 컴포넌트와 Details 경로에 해당하는 DetailsScreen 컴포넌트가 있다. stack의 초기 경로는 Home 경로이다. 
            - 주의
              ```
                component props는 컴포넌트를 받지 렌더링 함수를 받지는 않는다. inline function(예를 들어 component{() => <HomeScreen />})을 보내면 안된다.
              ```
        - Specifying options
            - 네이게이터에 있는 각 screen은 header에서 렌더링될 타이틀과 같은 일부 option들을 지정할 수 있다. 
              ```
                <Stack.Screen
                  name="Home"
                  component={HomeScreen}
                  options={{ title: 'Overview' }}
                />
              ```
            - 때때로 네비게이터에 있는 모든 screen들에 같은 option을 적용하고 싶을 때가 있다. 네비게이터에 screenOptions prop를 이용하면 가능하다.
        - Passing additional props
            - 때로는 screen에 추가적인 prop를 전달하고 싶을 때가 있다. 2가지 방식으로 접근이 가능하다.
                1. React context를 사용하고 context provider로 navigator를 감싸서 데이터를 화면으로 전달할 수 있다(권장)
                2. component prop을 지정하는 대신에 화면에 render callback을 사용하라
                  ```
                    <Stack.Screen name="Home">
                      {(props) => <HomeScreen {...props} extraData={someData} >}
                    </Stack.Screen>
                  ``` 
        - Summary
            - React Native는 웹 브라우저처럼 navigation을 위한 built-in API가 존재하지 않는다. React Navigation은 이와 함께 화면 간 전환을 위한
              iOS와 Android의 제스처와 애니메이션을 제공한다.
            - Stack.Navigator는 경로 구성을 하위 항목으로 삼고 구성을 위한 추가적인 propsd와 함께 컨텐츠를 렌더링하는 component이다.
            - 각 Stack.Screen 컴포넌트는 경로의 name을 참조하는 'name props'와 경로를 렌더링하는 특정한 컴포넌트인 'component props'를 가진다. 이 2가지는 반드시 필요하다.
            - stack의 초기 경로를 지정하려면 initialRouteName props를 제공하라.
    - Moving between screens
        - 웹 브라우저에서 화면을 이동하려면 다음과 같이 진핼할 수 있다.
          `<a href="details.html">Go to Details</a>`
        - 이런 방식으로 진행할 수도 있다.
          ```
            <a
              onClick={() => {
                window.location.href = 'details.html';
              }}
            >
              Go to Details
            </a>
          ```
        - Navigating to a new screen
            ```
              import * as React from 'react';
              import { Button, View, Text } from 'react-native';
              import { NavigationContainer } from '@react-navigation/native';
              import { createNativeStackNavigator } from '@react-navigation/native-stack';

              function HomeScreen({ navigation }) {
                return (
                  <View style={{ flex: 1, alignItems: 'center', justifyContents: 'center' }}>
                    <Text>Home Screen</Text>
                    <Button
                      title: "Go to Details"
                      onPress: {() => navigation.navigate('Details')}
                    />
                  </View>
                );
              }
            ```
            - 이를 분석해보자
                1. navigation: navigation props는 native stack navigator의 모든 screen component에 전달된다.
                2. navigate('Details'): 이동하려는 경로의 name을 사용하는 navigate 함수를 호출한다.
        - Navigate to a route multiple times
            ```
              function DetailsScreen({ navigation }) {
                return (
                  <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
                    <Text>Details Screen</Text>
                    <Button
                      title="Go to Details... again"
                      onPress={() => navigation.navigate('Details')}
                    />
                  </View>
                );
              }
            ```
            - navigate 함수는 대략적으로 이 화면으로 이동이라는 의미이며, 만약 이미 이 화면에 있다면 아무것도 하지 않는 것이 합리적이다.
            - 다른 details screen을 추가하고 싶다고 가정해보자. 이는 각 경로에 고유한 데이터를 전달할 때 매우 일반적인 경우이다. 이를 위해 'navigate'를
              'push'로 바꿀 수 있다. 이는 기존 navigation history와 관계 없이 다른 경로를 추가하려는 의도를 표현할 수 있다.
              ```
                <Button
                  title="Go to Details... again"
                  onPress={() => navigation.push('Details')}
                />
              ```
        - Going back
            - native stack navigator가 제공하는 header는 현재 screen에서 뒤로갈 수 있는 경우에 자동으로 뒤로가기 버튼을 포함한다.
            - 프로그래밍적으로 이 행위를 하려면 navigation.goBack()을 이용하면 된다.
              ```
                function DetailsScreen({ navigation }) {
                  return (
                    <View style={{ flex: 1, alignItems: 'center', justifyContents: 'center' }}>
                      <Text>Details Screen</Text>
                      <Button
                        title="Go to Details... again"
                        onPress={() => navigation.push('Details')}
                      />
                      <Button title="Go to Home" onPress={() => navigation,navigate('Home')} />
                      <Button title="Go back" onPress{() => navigation.goBack()} />
                    </View>
                  )
                }
              ```
    - Passing parameters to routes
    - Configuring the header bar
    - Header buttons
    - Nesting navigators
    - Navigation lifecycle
- Guides
    - Tab navigation
    - Drawer navigation
    - Supporting safe areas
- Navagators

### React Native Framework

#### Expo
- 

## native app
- 앱 개발 시 네이티브 코드를 사용하여 앱을 개발하는 방식

### Swift
- Language Guide
  - The Basics
  - Basic Operators
  - Strings and Characters
  - Collection Types
  - Control Flow
  - Functions
  - Closures
  - Enumerations
  - Structures and Classes
  - Properties
  - Methods 
- 기타
  - 애플의 iOS, macOS 드 자사의 제품 개발에 활용하는 프로그래밍 언어
  - 언어적 특성
      - 안정성 : 엄격한 문법
      - 신속성 : 실행 속도의 최적화, 컴파일러를 지속적으로 개량해 더 빠른 컴파일 성능 구현을 지향
      - 다중 패러다임 프로그래밍 : 명령형, 객체지향, 함수형, 프로토콜 지향 프로그래밍 패러다임을 차용
  - 스위프트의 변수와 상수
      - var : 변수 키워드
        `var [변수명]: [데이터 타입] = [값]` 형태로 선언하며, 데이터 타입은 생략 가능
      - let : 상수 키워드
        `let [상수명]: [데이터 타입] = [값]`

### Kotlin
- 안드로이드 앱 개발을 위한 언어
- 자바와 완전히 호환되는 언어
- 안드로이드 공식 언어
- 안드로이드 스튜디오에서 자바 대신 사용할 수 있다.

## web app
- 웹 브라우저를 통해 앱을 사용하는 방식

<hr />