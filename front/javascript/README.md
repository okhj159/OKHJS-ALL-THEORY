# JavaScript

## 목차
1. [JavaScript](#JavaScript)

## JavaScript
- References
    - Tutorials
        - intermediate
            - Closures
                - 클로저는 주변 상태(랙시컬 환경)를 참조하는 함수의 조합이다. 즉, 클로저는 내부 함수에서 외부 함수의 범위에
                  대한 엑세스를 제공한다. 자바스크립트에서는 함수가 생성될 때마다 클로저가 생성된다.
                - Lexical scoping
                    - 다음 예시 코드를 살펴보자.
                    - ```
                      function init() {
                         var name = "Mozilla"; // name is a local variable created by init
                         function displayName() {
                            // displayName() is the inner function, that forms the closure
                            console.log(name); // use variable declared in the parent function
                         }
                         displayName();
                         }
                      init();
                      ```
                    - init()은 로컬 변수인 name과 displayName()이라는 함수를 만들었다. displayName() 함수는
                      init() 안에 정의되어 있고, init() 함수 안에서만 유효하다. displayName() 함수에는 지역변수가 없다.
                      그러나, 내부 함수는 외부 함수의 변수에 접근할 수 있으므로, displayName()은 부모 함수인 init()에 선언된
                      name 변수에 접근할 수 있다.
                    - 이것이 함수가 중첩될 때, 파서가 변수 이름을 결정하는 방법을 설명하는 렉시컬 스코프의 예이다.
                      lexical이라는 단어는 렉시컬 스코프가 변수가 사용될 위치를 결정하기 위해 소스코드 내에서 선언된 위치를 사용한다는 사실을
                      보여주고 있다. 중첩된 함수는 외부 범위에 선언된 변수에 접근할 수 있다.
                    - 위 예에서 스코프는 function scope라고 한다. 변수가 접근가능하고, 선언된 함수 내에서만 접근 가능하기 때문이다.
                    - Scoping with let and const
                        - ES6 이전에 자바스크립트는 function scope와 global scope 둘만 존재하였다.
                          변수 선언을 var로 했을 시, 함수 내부냐 외부냐에 따라 function-scope, global-scope로 나뉘어졌다. 중괄호가 있는 블록은
                          scope를 생성하지 않기 때문에 다루기가 까다롭다.
                        - ```
                          if (Math.random() > 0.5) {
                            var x = 1;
                          } else {
                            var x = 2;
                          }
                          console.log(x);
                          ```
                        - 블록이 scope를 생성하는 다른 언어(C, JAVA 등) 사용자의 경우, 두 블록 모두에서 x의 범위를 벗어나기 때문에 위 코드에서 console.log는 에러를 낸다.
                          그러나, 블록은 var에 대한 scope를 생성하지 않기 때문에, 여기의 var 문은 전역 변수를 생성한다.
                        - ES6에서는 temporal dead zones과 같은 block-scope를 생성할 수 있는 let과 const 선언문을 소개하고 있다.
                        - ```
                          if (Math.random() > 0.5) {
                            const x = 1;
                          } else {
                            const x = 2;
                          }
                          console.log(x); // ReferenceError: x is not defined
                          ```
                - Closure
                    - 다음 예시 코드를 확인하자.
                    - ```
                      function makeFunc() {
                        const name = "Mozilla";
                        function displayName() {
                          console.log(name);
                        }
                        return displayName;
                        }
                      
                      const myFunc = makeFunc();
                      myFunc();
                      ```
- Guides
- 기타
    - 일반 함수과 화살표 함수에서 this의 차이
        - 일반 함수는 자신이 종속된 객체를 this로 가리키며, 화살표 함수는 종속된 인스턴스를 가리킨다.
          ```
          function BlackDog() {
            this.name = '흰둥이';
            return {
              name: '검둥이',
              bark: function() {
                console.log(this.name + ': 멍멍!');
              }
            }
          }
        
          const blackDog = new BlackDog();
          blackDog.bark(); // 검둥이: 멍멍!
        
          function WhiteDog() {
            this.name = '흰둥이';
            return {
              name: '검둥이',
              bark: () => {
                console.log(this.name + ': 멍멍!');
              }
            }
          }
        
          const whiteDog = new WhiteDog();
          whiteDog.bark(); // 흰둥이: 멍멍!
          ```
    - 화살표 함수는 따로 {}를 열어 주지 않으면 연산한 값을 그대로 반환한다는 의미이다.
      ```
      const triple = (value) => value * 3;
      ```
    - 자바스크립트에서 함수는 일급 객체다. 즉, 객체를 다루듯이 함수를 변수에 할당하거나, 함수를 다른 함수로
      전달하거나, 함수에서 함수를 반환하거나, 객체와 프로토타입에 할당하거나, 함수에 프로퍼티를 기록하거나,
      함수에 기록된 프로퍼티를 읽는 등의 작업을 할 수 있다.
    - 비동기 처리
        - 자바스크립트는 런타임에서 싱글 스레드로 동작하기 때문에 비동기 처리를 위해서는 콜백(callback), 프로미스(promise), 어싱크 어웨이트(async await) 방식을 사용한다.
        - 콜백
            - 함수의 파라미터로 함수를 전달
            - 가독성이 좋지 못하여 유지보수 및 디버깅이 힘들다.
        - 프로미스
            - 비동기 작업이 완료되면 결과를 반환하는 객체
            - then(), catch() 메서드를 사용하여 성공과 실패에 대한 처리가 가능하다.
        - 어싱크 어웨이트
            - 프로미스를 사용하는 비동기 작업을 동기적으로 처리하는 것처럼 코드를 작성할 수 있다.
            - async가 붙어 있는 함수를 실행할 때 await 키워드를 사용하여 비동기 작업이 완료될 때까지 기다릴 수 있다.
            - ```
              async function myName() {
                return "Andy";
              }
            
              async function showName() {
                const name = await myName(); // await는 promise 객체인 myName() 함수의 실행이 끝나길 기다린다.
                console.log(name);
              }
            
              console.log(showName());
              ```
    - 전개 연산자(...문법)를 사용하여 객체나 배열 내부의 값을 복사할 때는 얕은 복사를 하게 된다. 즉, 내부의
      값이 완전히 새로 복사되는 것이 아니라 가장 바깥쪽에 있는 값만 복사된다. 따라서 내부의 값이 객체 혹은
      배열이라면 내부의 값 또한 따로 복사해 주어야 한다.
      ```
      const todos = [{id: 1, checked: true}, {id:2, checked: true}];
      const nextTodos = [...todos];
    
      nextTodos[0].checked = false;
      console.log(todos[0] === nextTodos[0]); // 아직까지는 똑같은 객체를 가리키고 있기 때문에 true
    
      nextTodos[0] = {
        ...nextTodos[0],
        checked: false
      };
      console.log(todos[0] === nextTodos[0]); // 새로운 객체를 할당해 주었기에 false
      ```
    - immer를 사용하면 불변성을 유지하는 작업을 매우 간단하게 처리할 수 있다.
      ```
      import produce from 'immer';
      const nextState = produce(originalState, draft => {
        // 바꾸고 싶은 값 바꾸기
        draft.somewhere.deep.inside = 5;
      })
      ```
    - module.exports와 exports의 관계
        - 기본적으로 module.exports, exports 모두 하나의 객체를 바라보고 있는데, 최종적으로 return 되는 것은
          무조건 module.export이다.
        - 만약 exports에 다른 객체를 할당하게 되면, module.exports의 객체와 달라지게 되고, exports에 어떤 변경을 해도 모듈에는 영향을 주지 못한다.
          ```
            var module = {
                  exports: {}
            }
            var exports = module.exports;
          
            return module.exports;
          ```

<hr />