# Type Checkers

## 목차
1. [개요](#개요)
2. [TypeScript](#TypeScript)

## 개요
- 

## TypeScript
- Get Started
    - TypeScript for JavaScript Programmers
        - 타입 추론
            - 타입스크립트는 자바스크립트 언어를 알고 있으며 대부분의 경우 타입을 생성해준다. 예를 들어 변수를 생성하면서
              동시에 특정 값에 할당하는 경우, 타입스크립트는 그 값을 해당 변수의 타입으로 사용할 것이다.
        - 타입 정의
            - 자바스크립트는 클래스와 객체 지향 프로그래밍을 지원하기 때문에, 타입스크립트 또한 동일하다 - 인터페이스는 클래스로도
              선언할 수 있다.
            - ```
                interface User {
                  name: string;
                  id: number;
                }
              
                class UserAccount {
                  name: string;
                  id: number;
              
                  constructor(name: string, id: number) {
                    this.name = name;
                    this.id = id;
                  }
                }
              
                const user: User = new UserAccount("Murphy", 1);
              ```
- Handbook
    - Everyday Types
        - 객체 타입
            - 옵셔널 프로퍼티 
                - 객체 타입은 일부 또는 모든 프로퍼티의 타입을 선택적인 타입, 즐 옵셔널로 지정할 수 있다.
                  프로퍼티 이름 뒤에 ?를 붙이면 된다.
                - 자바스크립트에서는 존재하지 않는 프로퍼티에 접근하였을 때, 런타임 오류가 발생하지 않고 undefinded 값을
                  얻게 된다. 이 때문에 옵셔널 프로퍼티를 읽었을 때, 해당 값을 사용하기에 앞서 undefinded인지 여부를 확인해야 한다.
                  ```
                  function printName(obj: { first: string; last?: string }) {
                      // 오류 - `obj.last`의 값이 제공되지 않는다면 프로그램이 멈추게 됩니다!
                      console.log(obj.last.toUpperCase());
                  
                      'obj.last' is possibly 'undefined'.
                      
                      if (obj.last !== undefined) {
                          // OK
                          console.log(obj.last.toUpperCase());
                      }
                    
                      // 최신 JavaScript 문법을 사용하였을 때 또 다른 안전한 코드
                      console.log(obj.last?.toUpperCase());
                  }
                  ```
        - 유니언 타입
            - 유니언 타입 정의하기
                ```
              function printId(id: number | string) {
                  console.log("Your ID is: " + id);
              }
              // OK
              printId(101);
              // OK
              printId("202");
              // 오류
              printId({ myID: 22342 });
              Argument of type '{ myID: number; }' is not assignable to parameter of type 'string | number'.
                ```
            - 유니언 타입 사용하기
                - 타입스크립트에서 유니언을 다룰 떄는 해당 유니언 타입의 모든 멤버에 대하여 유효한 작업일 때에만 허용된다. 예를 들어
                  string | number라는 유니언 타입의 경우, string 타입에만 유효한 메서드는 사용할 수 없다.
                  ```
                  function printId(id: number | string) {
                      console.log(id.toUpperCase());
                      Property 'toUpperCase' does not exist on type 'string | number'.
                          Property 'toUpperCase' does not exist on type 'number'.
                  }
                  ```
                - 이를 해결하려면 코드상에서 유니언을 좁혀야 한다. 이는 타입 표기가 없는 자바스크립트에서 벌어지는 일과 동일하다.
                  좁히기란 타입스크립트가 코드 구조를 바탕으로 어떤 값을 보다 구체적인 타입으로 추론할 수 있을 때 발생한다.
                  ```
                  function printId(id: number | string) {
                      if (typeof id === "string") {
                          // 이 분기에서 id는 'string' 타입을 가집니다
                        
                          console.log(id.toUpperCase());
                      } else {
                          // 여기에서 id는 'number' 타입을 가집니다
                          console.log(id);
                      }
                  }
                  ```
                  또 다른 예시는 Array.isArray와 같은 함수를 사용하는 것이다.
                  ```
                  function welcomePeople(x: string[] | string) {
                      if (Array.isArray(x)) {
                          // 여기에서 'x'는 'string[]' 타입입니다
                          console.log("Hello, " + x.join(" and "));
                      } else {
                          // 여기에서 'x'는 'string' 타입입니다
                          console.log("Welcome lone traveler " + x);
                      }
                  }
                  ```
    - Object Types
        - Property Modifiers
            - Optional Properties
            - readonly Properties
            - Index Signatures
                - 유형 속성의 모든 이름은 모르지만, type을 알고 있는 경우에 사용할 수 있다.
                  <img src="type_checkers/typescript/index_signatures_1.png">
    - Type Manipulation
        - Generics
          ```
          1. 제네릭을 사용하지 않는 경우
          function identity(arg: number): number {
            return arg;
          }
          function identity(arg: any): any {
            return arg;
          }
        
        
          2. 제네릭을 사용하는 경우
          function identity<Type>(arg: Type): Type {
            return arg;
          }
          ```
- 기타
    - 변수 선언하는 방식은 다음과 같다.
      ```
      선언 키워드 변수명: 타입
      let a: number;
      ```
    - 선언 키워드 let과 var의 차이는 호이스팅 여부이다.
      var은 변수를 사용한 후에 선언이 가능하지만 let은 불가능하다.
    - arrow function의 경우 다음과 같이 타입을 지정한다.
      ```
      (인수명: 인수_타입): 반환값_타입 => 자바스크립트_식
      let sayHello = (name: string): string => `Hello ${name}`
      ```
    - 타입스크립트의 타입 시스템
        - 타입 애너테이션 방식
            - 타입을 명시적으로 선언해서 어떤 타입 값이 저장되는지를 컴파일러에 직접 알려주는 문법
            - 변수명 뒤에 :type 방식으로 작성
        - 구조적 타이핑
            - 이름으로 타입을 구분하는 명목적인 타입 언어의 특징과 달리 타입스크립트는 구조로 타입을 구분
            - ```
              interface Cartoon {
                price: number;
              }
            
              interface Novel {
                price: number;
              }
            
              let cartoon: Cartoon = { price: 3000 };
              let novel: Novel = { price: 12000 };
            
              cartoon = novel;
              novel = cartoon;
              // 타입이 서로 호환된다.
              ```
        - 구조적 서브타이핑
            - 객체의 프로퍼티를 바탕으로 타입을 구분
            - 이름이 다른 객체라도 가진 속성이 동일하다면 서로 호환 가능한 타입으로 간주함
    - 타입스크립트에서 지원하는 타입
        - 원시 값, 객체, 함수
        - any : 어떤 타입의 변수에도 할당 가능
        - unknown : 어떤 타입도 할당 가능하지만 다른 변수에 할당 또는 사용할 때 타입을 강제함
        - never : 어떤 값도 할당 불가능
    - 타입 리터럴 & 객체 리터럴
        - 타입 리터럴
            - 오직 하나의 값을 나타내는 타입
              ```
                let a = true     // boolean
                const c = true   // true => const 사용하여 선언하는 경우 값이 불변이기 때문에 타입스크립트는 가장 좁은 타입으로 추론한다.
              ```
        - 객체 리터럴
            - 객체(Object)를 생성하는 방법
              ```
                let a = {
                  b: 'x'
                }   // {b: string} 으로 추론된다.
              ```
            - cf) 객체는 const로 선언하는 경우 타입스크립트가 더 좁은 타입으로 추론하지 않는다.
              ```
                const timer: {count: number} = {
                  count: 12
                }   // {count: number}
              ```
    - 타입 구성하는 방법
        - 유니언 : `|`를 사용하여 여러 타입을 조합할 수 있다.
      ```
      function getLength(obj: string | string[]) {
        // obj는 sting 또는 string 배열 타입일 수 있음
      }
    
      type status = "Ready" | "Waiting" //변수가 가질 수 있는 값을 제한
      ```
        - 제네릭 : 어떤 타입이든 정의될 수 있지만 호출되는 시점에 타입이 결정된다.
    - 데커레이터를 활용하여 횡단 관심사를 분리하여 관점 지향 프로그래밍을 적용한 코드를 적용할 수 있다.
    - 에러처리
        - null 반환
            - 타입 안정성을 유지하면서 에러를 처리하는 가장 간단한 방법이다.
            - 로그를 일일이 확인해가며 디버깅을 해야 한다.
            - 모든 연산에서 null을 확인해야 하므로 연산을 중첩하거나 연결할 때 코드가 지저분해진다.
        - 예외 던지기
        - 예외 반환
            - 예외 반환을 한 것에 대해 처리해야 하며 그렇지 않으면 컴파일 타입에 TypeError가 발생한다.
        - Option 타입

<hr />