# Framework

## 목차
1. [개요](#개요)
2. [React](#React)
3. [React Library](#React-Library)

## 개요
- 

## React
- Learn
- Reference
    - 개요
        - React
            - React의 프로그래밍 기능
                - Hooks
                - Components
                - APIs
                - Directives
        - React DOM
            - React DOM은 브라우저 DOM 환경에서 실행되는 웹 애플리케이션에서만 지원되는 기능을 포함하고 있다.
                - Hooks
                - Components
                - APIs
                - Clients APIs
                - Server APIs
        - React의 규칙
            - 컴포넌트와 Hook은 순수해야 한다.
                - 순수성은 코드를 더 쉽게 이해하고 디버그할 수 있도록 하며, React가 올바르게 컴포넌트와 Hook을 자동으로 최적화할 수 있도록 한다.
            - React가 컴포넌트와 Hook을 호출하는 방식
                - React는 사용자 경험을 최적화하기 위해 필요할 때마다 컴포넌트와 Hook을 렌더링 한다.
            - Hook의 규칙
                - Hook은 JavaScript 함수로 정의되지만 호출 위치에 제약이 있는 특별한 유형의 재사용 가능한 UI 로직이다.
    - React
        - Hools
            - State Hooks
                - State를 통해 컴포넌트는 사용자 입력과 같은 정보를 기억할 수 있다. 예를 들어, 폼 컴포넌트는 state를 사용하여 입력값을 저장할 수 있고, 이미지
                  갤러리 컴포넌트는 state를 사용하여 선택한 이미지 인덱스를 저장할 수 있다.
                - 컴포넌트에 state를 추가하려면, 다음 Hook 중 하나를 사용하면 된다.
                    - useState는 직접 업데이트할 수 있는 state 변수를 선언한다.
                    - useReducer는 reducer 함수 내부의 업데이트 로직을 사용하여 state 변수를 선언한다.
            - Context Hooks
                - Context를 사용하면 컴포넌트가 멀리 있는 부모 컴포넌트로부터 props로 전달하지 않으면서 정보를 받을 수 있다. 예를 들어, 애플리케이션의 최상위 컴포넌트는
                  현재 UI 테마를 아래의 모든 컴포넌트에 깊이와 상관없이 전달할 수 있다.
                    - useState는 context를 읽고 구독한다.
            - Ref Hooks
                - Ref를 사용하면 컴포넌트가 DOM 노드나 timeout ID와 같이 렌더링에 사용되지 않는 일부 정보를 보유할 수 있다. state와 달리, ref를 업데이트해도
                  컴포넌트가 다시 렌더링 되지 않는다. Ref는 React 패러다임의 탈출구이다. 내장된 브라우저 API와 같이, React가 아닌 시스템으로 작업해야 할 때 유용하다.
                    - useRef는 ref를 선언한다. 여기에는 어떤 값이라도 담을 수 있지만, 대부분 DOM 노드를 담는 데 사용된다.
                    - useImperativeHandle을 사용하면 컴포넌트에 노출되는 ref를 커스텀할 수 있다. 이는 드물게 사용된다.
            - Effect Hooks
                - Effects를 통해 컴포넌트를 외부 시스템에 연결하고 동기화할 수 있다. 여기에는 네트워크, 브라우저 DOM, 애니메이션, 다른 UI 라이브러리를 사용하여 작성된
                  위젯, 기타 React가 아닌 코드를 다루는 것이 포함된다.
                    - useEffect는 컴포넌트를 외부 시스템에 연결한다.
                - Effects는 React 패러다임의 탈출구이다. 애플리케이션의 데이터 흐름을 조정하기 위해 Effect를 쓰지 마시길. 외부 시스템과 상호 작용하지 않는다면, Effect가
                  필요하지 않을 수도 있다.
                - useEffect에는 타이밍 차이가 있지만 거의 사용되지 않는 두 가지 변형이 있다.
                    - useLayoutEffect는 브라우저가 화면을 다시 그리기 전에 실행된다. 여기에서 레이아웃을 계산할 수 있다.
                    - useInsertionEffect는 React가 DOM을 변경하기 전에 실행된다. 라이브러리는 여기에 동적 CSS를 삽입할 수 있다. 
            - Performance Hooks
                - 재렌더링 성능을 최적화하는 일반적인 방법은 불필요한 작업을 건너뛰는 것이다. 예를 들어, 이전 렌더링 이후 데이터가 변경되지 않은 경우 캐시된 계산을 재사용하거나
                  재렌더링을 건너뛰도록 React에 지시할 수 있다.
                      - useMemo를 사용하면 비용이 많이 드는 계산 결과를 캐시할 수 있다.
                      - useCallback을 사용하면 함수 정의를 최적화된 컴포넌트에 전달하기 전에 캐시할 수 있다.
                - 화면을 실제로 업데이트해야 하므로 재렌더링을 건너뛸 수 없는 경우도 있다. 이 경우, 동기식이어야 하는 blocking 업데이트(예: input에 입력)와 사용자
                  인터페이스를 차단할 필요가 없는 non-blocking 업데이트(예: 차트 업데이트)를 분리하여 성능을 향상시킬 수 있다.
                - 렌더링 우선순위를 지정하려면, 다음 Hook 중 하나를 사용하면 된다.
                    - useTransition을 사용하면 state 전환을 non-blocking으로 표시하고, 다른 업데이트가 이를 중단하도록 허용할 수 있다.
                    - useDefferredValue를 사용하면 UI의 중요하지 않은 부분에 대한 업데이트를 연기하고, 다른 부분이 먼저 업데이트되도록 할 수 있다.
            - Other Hooks
                - 다음 Hook은 대부분 라이브러리 작성자에게 유용하며 애플리케이션 코드에서는 일반적으로 사용되지 않는다.
                    - useDebugValue를 사용하면 커스텀 Hook에 대해 React DevTools에 표시해 주는 레이블을 커스텀할 수 있다.
                    - useId를 사용하면 컴포넌트가 고유 ID를 자신과 연결할 수 있다. 일반적으로 접근성 API와 함께 사용된다.
                    - useSyncExternalStore를 사용하면 컴포넌트가 외부 저장소를 구독할 수 있다.
                    - useActionState를 사용하면 액션을 통해 상태를 관리할 수 있다.
            - Custom Hooks
                - 나만의 custom hook을 정의할 수도 있다.
        - 컴포넌트
            - 내장 컴포넌트
                - `<Fragment>`, 또는 `<>...</>`로 표기하며, 여러 JSX 노드를 함께 그룹화할 수 있다.
                - `<Profiler>` React 트리의 렌더링 성능을 프로그래밍적으로 측정할 수 있다.
                - `<Suspense>`자식 컴포넌트를 로딩하는 동안 fallback을 표시할 수 있다.
                - `<StrictMode>` 초기에 버그를 찾는 데 도움이 되는 추가 개발 전용 검사를 사용할 수 있다.
            - Custom 컴포넌트
                - 나만의 custom component를 정의할 수도 있다.
            - `<Suspense>`
                - `<Suspense>`는 자식 요소가 로드되기 전까지 화면에 대체 UI를 보여준다.
                - 레퍼런스
                    - props
                        - children: 궁극적으로 렌더링하려는 실제 UI이다. children의 렌더링이 지연되면, Suspense는 fallback을 대신 렌더링한다.
                        - fallback: 실제 UI가 로드되기 전까지 대신 렌더링 되는 대체 UI이다. 올바른 React node 형식은 무엇이든 대체 UI로 활용할 수 있지만, 실제로는
                          보통 로딩 스피너나 스켈레톤처럼 간단한 placeholder를 활용한다. Suspense는 children의 렌더링이 지연되면 자동으로 fallback으로 전환하고,
                          데이터가 준비되면 children으로 다시 전환한다. 만약 fallback의 렌더링이 지연되면, 가장 가까운 부모 Suspense가 활성화된다.
                    - 주의사항
                        - React는 컴포넌트가 처음으로 마운트 되기 전에 지연된 렌더링을 하는 동안의 어떤 state도 유지되지 않는다. 컴포넌트가 로드되면 React는
                          일시 중지된 트리를 처음부터 다시 렌더링한다.
                        - Suspense가 트리의 콘텐츠를 보여주고 있을 때 또다시 지연되면 startTransition나 useDeferredValue로 인한 업데이트가 아닌 한, fallback이
                          다시 보인다.
                        - React가 다시 일시 중지되어 보이는 콘텐츠를 숨겨야 하는 경우, 콘텐츠 트리에서 layout Effect들을 정리한다. 콘텐츠가 다시 보일 준비가 되면
                          React는 layout Effect들을 다시 실행한다. 이로써 DOM 레이아웃을 측정하는 Effect가 콘텐츠가 숨겨져 있는 동안 동작하지 않도록 보장한다.
                        - React는 Supense와 통합된 Streaming Server Rendering와 Selective Hydration같은 내부 최적화를 포함하고 있다.
                - 사용법
                    - 콘텐츠가 로드되는 동안 대체 UI 보여주기
                        - 애플리케이션의 모든 곳을 Suspense 경계로 감쌀 수 있다.
                          ```
                            <Suspense fallback={<Loading />}>
                              <Albums />
                            </Suspense>
                          ```
                        - React는 children에 필요한 모든 코드와 데이터가 로드될 때까지 loading fallback을 보여준다.
                        - 중요
                          ```
                            Suspense가 가능한 데이터만이 Suspense 컴포넌트를 활성화한다. 아래와 같은 것들이 해당된다.
                            - Relay와 Next.js같이 Suspense가 가능한 프레임워크를 사용한 데이터 가져오기
                            - lazy를 활용한 지연 로딩 컴포넌트
                            - use를 사용해서 Promise 값 읽기
                            Suspense는 Effect 또는 이벤트 핸들러 내부에서 가져우는 데이터를 감지하지 않는다.
                          ```
                    - 콘텐츠를 한꺼번에 함께 보여주기
                        - 기본적으로 Suspense 내부의 전체 트리는 하나의 단위로 취급된다. 예를 들어, 이러한 구성 요소 중 하나라도 어떤 데이터에 의해 지연되더라도 모든
                          구성 요소가 함께 로딩 표시로 대체된다.
                          ```
                            <Suspense fallback={<Loading />}>
                              <Biography />
                              <Panel>
                                <Albums />
                              </Panel>
                            </Suspense>
                          ```
                        - 그런 다음 모두 보일 준비가 되면 한꺼번에 모두 함께 보인다.
                    - 중첩된 콘텐츠가 로드될 때 보여주기
                        - 컴포넌트가 일시 중단되면 가장 가까운 상위 Suspense 컴포넌트가 Fallback을 보여준다. 이를 통해 여러 Suspense 컴포넌트를 중첩하여 로딩 순서를
                          만들 수 있다. 각 Suspense의 Fallback은 다음 레벨의 콘텐츠를 사용할 수 있게 되면 채워진다. 예를 들어 앨범 목록에 자체 Fallback을 지정할 수 있다.
                          ```
                            <Suspense fallback={<BigSpinner />}>
                              <Biography />
                              <Suspense fallback={<AlbumsGlimmer />}>
                                <Panel>
                                  <Albums />
                                </Panel>
                              </Suspense>
                            </Suspense>
                          ```
                        - 이 변경으로 Biography를 보여줄 때 Albums이 로드될 떄까지 기다릴 필요가 없다.
                        - 순서는 다음과 같다.
                          1. Biography가 아직 로드되지 않은 경우, 전체 콘텐츠 영역 대신 BigSpinner가 표시된다.
                          2. Biography 로딩이 완료되면 BigSpinner가 콘텐츠로 대체된다.
                          3. Albums가 아직 로드되지 않으면 Albums와 그 상위 Panel 대신 AlbumsGlimmer가 표시된다.
                          4. 마지막으로 Albums가 로딩을 완료하면 AlbumsGlimmer를 대체한다.
                        - Suspense를 사용하면 UI의 어떤 부분이 항상 동시에 그려져야 하는지, 어떤 부분이 로딩 순서에서 점진적으로 더 많은 콘텐츠를 보여줘야 하는지
                          조정할 수 있다. 앱의 나머지 동작에 영향을 주지 않고 트리의 어느 위치에서나 Suspense를 추가, 이동 또는 삭제할 수 있다.
                        - 모든 컴포넌트 주위에 Suspense를 두면 안된다. Suspense는 사용자가 경험하기를 원하는 로딩 순서보다 더 세분화되어서는 안된다.
                          디자이너와 함께 작업하는 경우 로딩 상태를 어디에 배치해야 하는지 디자이너에게 물어보면 된다. 디자이너가 이미 디자인 와이어 프레임에
                          포함했을 가능성이 높다.
                    - 새 콘텐츠가 로드되는 동안 이전 콘텐츠 보여주기
                        - 예시
                          ```
                            export default function App() {
                              const [query, setQuery] = useState('');
                              return (
                                <>
                                  <label>
                                    Search albums:
                                    <input value={query} onChange={e => setQuery(e.target.value)} />
                                  </label>
                                  <Suspense fallback={<h2>Loading...</h2>}>
                                    <SearchResults query={query} />
                                  </Suspense>
                                </>
                              );
                            }
                          ```
                        - 위 예시에서는 검색 결과를 가져오는 동안 SearchResults 컴포넌트가 지연된다. "a"를 입력하고 결과를 기다인 다음 "ab"로 바꾸면 "a"에 대한
                          결과는 로딩 Fallback으로 바뀐다.
                        - 일반적인 대체 UI 패턴은 목록들에 대한 업데이트를 연기하고 새 결과가 준비될 때까지 이전 결과를 계속 보여주는 것이다. useDeferredValue Hook을
                          사용하면 쿼리의 지연된 버전을 아래로 전달할 수 있다.
                          ```
                            export default function App() {
                              const [query, setQuery] = useState('');
                              const deferredQuery = useDeferredValue(query);
                              return (
                                <>
                                  <label>
                                    Search albums:
                                    <input value={query} onChange={e => setQuery(e.target.value)} />
                                  </label>
                                  <Suspense fallback={<h2>Loading...</h2>}>
                                    <SearchResults query={deferredQuery} />
                                  </Suspense>
                                </>
                              );
                            }
                          ```
                        - query는 즉시 업데이트되므로 입력에 새 값이 표시된다. 그러나 deferredQuery는 데이터가 로드될 때까지 이전 값을 유지하므로
                          SearchResults는 잠시 동안 이전 결과를 보여준다.
                        - 사용자에게 더 명확하게 알리기 위해 이전 결과 목록이 표시될 때 시각적 표시를 추가할 수 있다.
                          ```
                            <div style={{
                              opacity: query !== deferredQuery ? 0.5 : 1 
                            }}>
                              <SearchResults query={deferredQuery} />
                            </div>
                          ```
                        - 아래 예시에서 "a"를 입력하고 결과가 로드될 때까지 기다린 다음 입력을 "ab"로 편집해 보자. 이제 새 결과가 로드될 때까지 Suspense Fallback 대신
                          희미한 이전 결과 목록이 표시되는 것을 확인할 수 있다.
                          ```
                            import { Suspense, useState, useDeferredValue } from 'react';
                            import SearchResults from './SearchResults.js';

                            export default function App() {
                              const [query, setQuery] = useState('');
                              const deferredQuery = useDeferredValue(query);
                              const isStale = query !== deferredQuery;
                              return (
                                <>
                                  <label>
                                    Search albums:
                                    <input value={query} onChange={e => setQuery(e.target.value)} />
                                  </label>
                                  <Suspense fallback={<h2>Loading...</h2>}>
                                    <div style={{ opacity: isStale ? 0.5 : 1 }}>
                                      <SearchResults query={deferredQuery} />
                                    </div>
                                  </Suspense>
                                </>
                              );
                            }
                          ```
                        - 중요!
                          ```
                            지연된 값(deferred value)과 Transitions을 사용하면 Suspense fallback 을 표시하지 않을 수 있다. Transitions는 전체
                            업데이트를 긴급하지 않은 것으로 처리하므로 일반적으로 프레임워크와 router 라이브러리에서 navigation을 위해 사용된다. 반면에
                            지연된 값(deferred value)은 UI의 일부를 긴급하지 않은 것으로 처리하고 나머지 UI보다 지연시키려는 목적의 애플리케이션 코드에서 유용하다. 
                          ```
                    - 이미 보인 콘텐츠가 숨겨지지 않도록 방치
                        - 컴포넌트가 지연되면 가장 가까운 상위 Suspense가 Fallback을 보여주도록 전환한다. 이미 일부 콘텐츠가 보이는 경우 사용자 경험이 끊길 수 있다.
                          ```
                            import { Suspense, useState } from 'react';
                            import IndexPage from './IndexPage.js';
                            import ArtistPage from './ArtistPage.js';
                            import Layout from './Layout.js';

                            export default function App() {
                              return (
                                <Suspense fallback={<BigSpinner />}>
                                  <Router />
                                </Suspense>
                              );
                            }

                            function Router() {
                              const [page, setPage] = useState('/');

                              function navigate(url) {
                                setPage(url);
                              }

                              let content;
                              if (page === '/') {
                                content = (
                                  <IndexPage navigate={navigate} />
                                );
                              } else if (page === '/the-beatles') {
                                content = (
                                  <ArtistPage
                                    artist={{
                                      id: 'the-beatles',
                                      name: 'The Beatles',
                                    }}
                                  />
                                );
                              }
                              return (
                                <Layout>
                                  {content}
                                </Layout>
                              );
                            }

                            function BigSpinner() {
                              return <h2>🌀 Loading...</h2>;
                            }

                          ```
                          ```
                            export default function ArtistPage({ artist }) {
                              return (
                                <>
                                  <h1>{artist.name}</h1>
                                  <Biography artistId={artist.id} />
                                  <Suspense fallback={<AlbumsGlimmer />}>
                                    <Panel>
                                      <Albums artistId={artist.id} />
                                    </Panel>
                                  </Suspense>
                                </>
                              );
                            }

                            function AlbumsGlimmer() {
                              return (
                                <div className="glimmer-panel">
                                  <div className="glimmer-line" />
                                  <div className="glimmer-line" />
                                  <div className="glimmer-line" />
                                </div>
                              );
                            }

                          ```
                        - 버튼을 눌렀을 때 Router 컴포넌트가 IndexPage 대신 ArtistPage를 렌더링했다. ArtistPage 내부의 컴포넌트가 지연됐기 때문에 가장
                          가까운 Suspense가 Fallback을 보여주기 시작했다. 가장 가까운 Suspense가 root 근처에 있었기 때문에 전체 사이트 레이아웃이 BigSpinner로
                          대체되었다.
                        - 이를 방지하려면 startTransition을 사용하여 navigation state 업데이트를 Transition으로 처리할 수 있다.
                          ```
                            function Router() {
                            const [page, setPage] = useState('/');

                            function navigate(url) {
                              startTransition(() => {
                                setPage(url);      
                              });
                            }
                            // ...
                          ```
                        - 이는 state 전환이 급하지 않으며, 이미 공개된 콘텐츠를 숨기는 대신 이전 페이지를 계속 표시하는 것이 좋다는 것을 React에게 알려준다. 이제
                          버튼을 클릭하면 Biography가 로드될 떄까지 대기한다.
                          ```
                            import { Suspense, startTransition, useState } from 'react';
                            import IndexPage from './IndexPage.js';
                            import ArtistPage from './ArtistPage.js';
                            import Layout from './Layout.js';

                            export default function App() {
                              return (
                                <Suspense fallback={<BigSpinner />}>
                                  <Router />
                                </Suspense>
                              );
                            }

                            function Router() {
                              const [page, setPage] = useState('/');

                              function navigate(url) {
                                startTransition(() => {
                                  setPage(url);
                                });
                              }

                              let content;
                              if (page === '/') {
                                content = (
                                  <IndexPage navigate={navigate} />
                                );
                              } else if (page === '/the-beatles') {
                                content = (
                                  <ArtistPage
                                    artist={{
                                      id: 'the-beatles',
                                      name: 'The Beatles',
                                    }}
                                  />
                                );
                              }
                              return (
                                <Layout>
                                  {content}
                                </Layout>
                              );
                            }

                            function BigSpinner() {
                              return <h2>🌀 Loading...</h2>;
                            }
                          ```
                        - Transition은 모든 콘텐츠가 로드될 떄까지 기다리지 않는다. 이미 보여진 콘텐츠가 숨겨지지 않도록 충분히 오래 기다린다. 예를 들어 웹사이트
                          Layout은 이미 보이므로 로딩 스피너 뒤에 숨기는 것은 좋지 않다. 그러나 Albums 주위에 중첩된 Suspense는 새로운 것이므로 Transition이
                          기다리지 않는다.
                    - Transition이 발생하고 있음을 보여주기
        - API
    - React DOM
        - Hooks
        - 컴포넌트
        - API
        - 클라이언트 API
        - 서버 API
    - React의 규칙
    - React 서버 컴포넌트
- 기타
    - 네이밍 규칙
        - 컴포넌트가 단일 파일로 구성되는 경우 파일 이름은 대문자로 시작해야 한다.
          `MyComponent.js`와 같이 작성하며, 이는 해당 파일이 React 컴포넌트를 정의하고 있다는 것을 명시적으로 나타내기 위함이다.
        - 일반적인 JavaScript 함수 또는 유틸리티 함수를 정의하는 파일은 소문자로 시작한다. `helperFunctions.js`와 같이 소문자로 시작한다.
          ```
          const add = (a, b) => {
            return a + b;
          };
          
          export { add };
          ```
    - 클래스형 컴포넌트와 함수형 컴포넌트
        | 기능      | 클래스형 컴포넌트      | 함수형 컴포넌트  |  
        |---------|----------------|-----------|
        | state   | 사용 가능          | 사용 불가능    |
        | 라이프 사이클 | 라이프 사이클 API 사용 | hooks 사용  |
        | 자원 사용   | 비교적 많이 사용      | 비교적 적게 사용 |
    
    - JSX 코드는 브라우저에서는 직접 해석할 수 없으므로, 웹팩에 의해 자바스크립트 코드로 변환된다.
      이때, JSX로 구현된 컴포넌트는 자바스크립트의 객체로 표현된다. 변환된 자바스크립트 코드를
      브라우저가 읽어서 실행하고 화면을 그리기 시작한다.
    - 리액트에서 DOM 요소에 스타일을 적용할 떄는 문자열 형태로 넣는 것이 아니라 객체 형태로
      넣어 주어야 한다. 스타일 이름 중에서 background-color처럼 - 문자가 포함되는 이름이 있으면,
      하이픈(-) 문자를 없애고 카멜 표기법으로 작성해야 한다.
    - component
        - 라이프사이클 메서드 흐름
          <img alt="Component_lifecycle_method_flow" src="react/Component_lifecycle_method_flow.png">
    - Hooks
        - 상태 훅
            - useState
            - useEffect
            - useReducer
                - userReducer()의 반환값 배열의 첫 번째는 현재 상태, 두 번째는 dispatch 함수이다.
                  dispatch 함수에 action을 전달함으로써 상태를 업데이트할 수 있다.
                - reducer가 현재 상태와 action을 기반으로 다음 상태를 결정한다.
                  ```
                  impport {useReducer} from 'react';
                  
                  function reducer(state, action) {
                    // action.type에 따라 다른 작업 수행
                    switch (action.type) {
                      case 'INCREMENT':
                        return { value: state.value + 1 };
                      case 'DECREMENT':
                        return { value: state.value - 1 };
                      default:
                        // 아무것도 해당되지 않을 떄 기존 상태 반환
                        return state;
                    }
                  }
                  
                  const Counter = () => {
                    const [state, dispatch] = useReducer(reducer, { value: 0 });
                  
                    return (
                      <div>
                        <p>
                          현재 카운터 값은 <b>{state.value}</b>입니다.
                        </p>
                        <button onClick={() => dispatch({ type: 'INCREMENT' })}>+1</button>
                        <button onClick={() => dispatch({ type: 'DECREMENT' })}>-1</button>
                      </div>
                    );
                  };
                  ```
                - useReducer를 사용했을 때의 가장 큰 장점은 컴포넌트 업데이트 로직을 컴포넌트 바깥으로
                  빼낼 수 있다는 점이다.
        - 메모이제이션 훅
            - useMemo
            - useCallback
                - useMemo는 특정 결과값을 재사용 할 때 사용하는 반면, useCallback은 특정 함수를 새로 만들지 않고
                  재사용하고 싶을 때 사용한다.
        - 라우팅 관련 훅
            - useParams
            - useSearchParams
        - useContext
            - useContext는 컴포넌트에서 context를 읽고 구독할 수 있게 해주는 리액트 hook이다.
        - 기타
            - useRef
                - 함수 컴포넌트에서 ref를 쉽게 사용할 수 있도록 한다. useRef를 사용하여 ref를
                  사용하여 ref를 설정하면 useRef를 통해 만든 객체 안의 current 값이 실제 엘리먼트를 가리킨다.
                - 컴포넌트 로컬 변수를 사용해야 할 때도 useRef를 활용할 수 있다. 여기서 로컬 변수란
                  렌더링과 상관없이 바뀔 수 있는 값을 의미한다.
                - useRef의 주요 이점
                    1. DOM 요소에 접근
                    - 가장 일반적으로 'useRef'는 함수 컴포넌트에서 DOM 요소에 접근하는 데 사용된다. 'useRef'로 생성한
                      객체의 'current'속성을 통해 해당 DOM 요소에 직접 접근 가능
                      ```
                       import React, { useRef, useEffect } from 'react';
           
                       const MyComponent = () => {
                          const myRef = useRef(null);
                          
                          useEffect(() => {
                             // myRef.current를 통해 DOM 요소에 접근
                             console.log(myRef.current);
                          }, []);
                          
                          return <div ref={myRef}>Hello, World!</div>;
                       };
                      ```
                    2. 컴포넌트 간 통신
                    - 'useRef'는 컴포넌트 간에 값을 공유하고 통신하는 데에도 사용될 수 있다. 예를 들어, 자식 컴포넌트에서 부모
                      컴포넌트의 상테를 업데이트하고 싶을 때 활용할 수 있다.
                      ```
                        import React, { useRef } from 'react';
          
                        const ParentComponent = () => {
                           const sharedValueRef = useRef('initial value');
                           
                           const ChildComponent = () => {
                              // 부모 컴포넌트의 ref를 통해 값 읽기
                              console.log(sharedValueRef.current);
                           
                              // 부모 컴포넌트의 ref를 통해 값 업데이트
                              sharedValueRef.current = 'new value';
                           };
                           
                           return (
                              <div>
                                 <ChildComponent />
                              </div>
                           );
                        };
                      ```
                    3. 컴포넌트 렌더링과 무관한 값 저장
                    - 'useRef'에 저장된 값은 컴포넌트가 리렌더링될 때 변경되지 않는다. 따라서 'useRef'를 사용하면
                      값이 변경되더라도 컴포넌트가 다시 렌더링되지 않는다.
                      ```
                        import React, { useRef, useState } from 'react';
          
                        const MyComponent = () => {
                           const renderCount = useRef(0);
                           
                           // 컴포넌트 렌더링 횟수 증가 (재렌더링되어도 값이 유지됨)
                           renderCount.current += 1;
                           
                           const [state, setState] = useState('initial state');
                           
                           return (
                              <div>
                                 <p>Render count: {renderCount.current}</p>
                                 <button onClick={() => setState('new state')}>Update State</button>
                              </div>
                           );
                        };
                      ```
        - useCallback vs useEffect
            - useCallback
                - 콜백함수를 자식에게 전달해줄 때 사용
                - 자주 렌더링 위험이 있는 요소를 성능 최적화를 위해 사용
                - const onChange = useCallback(e => {...}); 이렇게 지정하고 자식에게 던진다
            - useEffect
                - 사이드 이펙트 방지를 위해 사용
                - API 통신(data fetch), 이벤트 리스너 추가, DOM 업데이트 등
                - useEffect(()=>{...}); 함수 호출을 통해, 실행한다
    - default props & default parameter
        - 리액트 18.2 버전까지 방식 deprecated
          ```
          const GreetComponent = ({ name, age }) => (
            <div>{`Hello, my name is ${name}, ${age}`}</div>
          );
          GreetComponent.defaultProps = {name: 'oklee', age: 25};
          ```
        - 리액트 18.3 버전 이후
          ```
          const GreetComponent = ({ name = 'oklee', age = 25 }) => (
            <div>{`Hello, my name is ${name}, ${age}`}</div>
          );
          ```
    - 컴포넌트 스타일링
        - 일반 CSS
        - Sass
            - 자주 사용되는 CSS 전처리기 중 하나로 확장된 CSS 문법을 사용하여 CSS 코드를 더욱 쉽게 작성할 수 있도록 해준다.
        - CSS Module
            - 스타일을 작성할 때 CSS 클래스가 다른 CSS 클래스의 이름과 절대 충돌하지 않도록 파일마다 고유한 이름을
              자동으로 생성해 주는 옵션이다.
        - styled-components
            - 스타일을 자바스크립트 파일에 내장시키는 방식으로 스타일을 작성함과 동시에 해당 스타일이 적용된 컴포넌트를
              만들 수 있게 해준다.
            - Tagged 템플릿 리터럴
                - 스타일을 작성할 때 `을 사용하여 만든 문자열에 스타일 정보를 넣을 수 있는데, 이 문법을 Tagged 템플릿 리터럴
                  이라고 부른다. CSS Module에 사용하는 일반 템플릿 리터럴과 다른 점은 템플릿 안에 자바스크립트 객체나 함수를
                  전달 할 때 온전히 추출할 수 있다는 것이다.
    - context
        - Provider를 사용할 때 value를 명시하지 않으면 오류가 발생한다.
    - 리렌더링 조건
        - React가 리렌더링되는 때는 다음과 같다
            - state가 업데이트 되었을 때
            - 부모 컴포넌트가 리렌더링 되었을 때
            - props가 업데이트 되었을 때
                - 같은 props를 받게되더라도 리렌더링이 발생하는데, 이를 방지하기 위해 React.memo()를 사용할 수 있다.
- 기타 라이브러리 
    - router
        - 리액트 라우터
            - Getting Started
                - Feature Overview
                    - Client Side Routing
                    - Nested Routes
                    - Dynamic Segments
                    - Ranked Route Matching
                    - Active Links
                    - Relative Links
                    - Data Loading
                    - Redirects
                    - Pending Navigation UI
                    - Skeleton UI with `<Suspense>`
                    - Data Mutation
                    - Data Revalidation
                    - Busy Indicators
                    - Optimistic UI
                    - Data Fetchers
                - Main Concepts
            - Routers
                - Picking a Router
                - createBrowserRouter
            - Router Components
                - BrowserRouter
                - NativeRouter
                - Router
            - Route
                - Route
                - action
                - loader
            - Components
                - Await
                - Form
                - Link
                - Outlet
                    - 이 컴포넌트는 Route의 children으로 들어가는 JSX 엘리먼트를 보여준다.
                - Route
                - Routes
            - Hooks
                - useActionData
                - useLocation
                - useOutlet
            - Guides
    - store
        - 리덕스
            - Introduction
                - Getting Started with Redux
                - Installation
                - Core Concepts
                - Ecosystem
            - Tutorials
            - Using Redux
            - Style Guide
            - 기타 
                - 리덕스의 3가지 규칙
                      1. 단일 스토어
                          - 하나의 애플리케이션 안에는 하나의 스토어가 들어 있다.
                      2. 읽기 전용 상태
                          - 리덕스 상태는 읽기 전용이다. 상태를 업데이트 할 때 기존의 객체는
                            건드리지 않고 새로운 객체를 생성해 주어야 한다.</br>
                            리덕스에서 불변성을 유지해야 하는 이유는 내부적으로 데이터가 변경되는
                            것을 감지하기 위해 얕은 비교 검사를 하기 때문이다.
                            객체의 변화를 감지할 때 겉만 비교하여 좋은 성능을 유지할 수 있다.
                      3. 리듀서는 순수한 함수
                          - 변화를 일으키는 리듀서 함수는 순수한 함수여야 한다. 순수한 함수는
                            다음 조건을 만족한다.
                              1. 리듀서 함수는 이전 상태와 액션 객체를 파라미터로 받는다.
                              2. 파라미터 외의 값에는 의존하면 안 된다.
                              3. 이전 상태는 절대로 건드리지 않고, 변화를 준 새로운 상태 객체를
                                 만들어서 반환한다.
                              4. 똑같은 파라미터로 호출된 리듀서 함수는 언제나 똑같은 결과 값을
                                 반환해야 한다.
        - zustand
            - 리덕스와의 비교
                - 상태 모델
                    - 개념적으로 Zustand와 Redux는 매우 유사하며 둘 다 불변 상태 모델을 기반으로 한다.
                      그러나 Redux를 사용하려면 앱을 context provider로 래핑해야한다. zustand는 그렇지 않다.
                - 렌더링 최적화
                    - 앱 내 렌더링 최적화와 관련하여 Zustand와 Redux의 접근 방식에는 큰 차이가 없다. 두 라이브러리 모두
                      선택기를 사용하여 렌더링 최적화를 수동으로 적용하는 것이 좋다.

## React Library

### Store

#### Redux

#### Redux Tookit
- Introduction
    - Getting started
        - Purpose
            - Redux의 3가지 문제를 해결하기 위해 만들어졌다.
                1. Redux store를 구성하는 것은 너무 복잡하다.
                2. Redux가 유용한 작업을 하려면 많은 패키지를 추가해야 한다.
                3. Redux는 많은 보일러플레이트 코드를 필요로 한다.
        - Installation
        - What's Included
            - Redux toolkit은 다음 API들을 포함하고 있다.
                - configureStore()
                - createReducer()
                - createAction()
                - createSlice()
                - createSlice()
                - combineSlices()
                - createAsyncThunk
                - createEntityAdaptor
        - RTK Query
            - What's included
                - RTK Query는 다음 API들을 포함하고 있다.
                    - createApi()
                    - fetchBaseQuery()
                    - `<ApiProvider />` 
                    - setupListeners
    - Why Redux Toolkit is How To Use Redux Today

#### MobX

#### Recoil

#### Zustand

<hr />