# DEVOPS

## 목차
1. [Cloud Providers](#Cloud-Providers)
2. [SERVERLESS](#SERVERLESS)

### Cloud Providers
#### AWS
- AWS S3
    - 데이터를 버킷 내의 객체로 저장하는 객체 스토리지 서비스이다.
      객체는 해당 파일을 설명하는 모든 메타데이터이고, 버킷은 객체에 대한 컨테이너이다.
      각 객체에 키(또는 키 이름)이 있으며, 이는 버킷 내 객체에 대한 고유한 식별자이다.
    - 데이터 일관성 모델
        - 버킷에 있는 객체의 PUT 및 DELETE 요청에 대해 강력한 쓰기 후 읽기(read-after-write) 일관성을 제공한다.
        - 동시 작성자에 대한 객체 잠금을 지원하지 않는다. 두 PUT 요청을 동시에 같은 키에 대해 실행할 경우 타임스탬프가 최신인 요청이 우선 적용된다.
    - AWS S3 액세스
        - AWS Management Console
        - AWS Command Line Interface
        - AWS SDK
        - Amazon S3 REST API
- AWS ECR
    - 도커 이미지 파일을 pull, push 할 수 있는 컨테이너 이미지 저장소이다.
- AWS ECS
    - 컨테이너화된 애플리케이션을 쉽게 배포, 관리, 스케일링할 수 있도록 도와주는 완전 관리형 컨테이너 오케스트레이션 서비스이다.
    - 구성요소
        - 용량
            - 컨테이너가 실행되는 인프라
            - 옵션
                1. AWS EC2 인스턴스
                2. AWS Fargate
                3. 온프레미스 가상머신(VM) 또는 서버
        - 컨트롤러
            - 컨테이너에서 실행되는 애플리케이션을 배포하고 관리
        - 프로비저닝
            - 스케줄러와 함께 애플리케이션 및 컨테이너를 배포 및 관리하는 데 사용할 수 있는 도구
            - 옵션
                1. AWS Management Console
                2. AWS Command Line Interface
                3. AWS SDK
                4. Copilot
                5. AWS CDK

<hr />

### SERVERLESS
#### AWS LAMBDA
- Lambda기본
    - Lambda는 빠르게 스케일 업해야 하고 수요가 없을 때는 0으로 스케일 다운해야 하는 애플리케이션 시나리오에 이상적인 컴퓨팅 서비스이다.
    - 개념
        - 함수
            - 함수는 Lambda에서 코드를 실행하기 위해 호출할 수 있는 리소스이다.
        - 트리거
            - 트리거는 Lambda에서 함수를 호출하는 리소스 또는 구성이다.
        - 이벤트
            - 이벤트는 처리할 Lambda 함수에 대한 데이터가 포함된 JSON 형식 문서이다.
        - 실행환경
          <img alt="Execution_environment" src="serverless/aws_lambda/Execution_environment.png">
            - 함수의 런타임은 런타임 API를 사용하여 Lambda와 통신한다. 익스텐션은 익스텐션 API를 사용하여
              Lambda와 통신한다. 또한 확장은 텔레메트리 API를 사용하여 함수의 로그 메시지와 기타 텔레메트리
              데이터를 수신할 수 있다.
    - Lambda 배포 패키지
        - .zip 파일 아카이브
            - Lambda 콘솔 사용
                1. Lambda 콘솔에서 함수 페이지를 연다
                2. 함수를 선택
                3. 코드 소스 창에서 업로드 원본을 선택한 다음 .zip 파일을 선택
                4. [업로드]를 선택하여 로컬 .zip 파일을 선택
                5. 저장을 선택
            - AWS CLI 사용
            - Amazon S3 사용
- 함수 배포
    - zip 파일 아카이브
        - Lambda 콘솔이나 도구 키트를 사용하여 함수를 작성하면 Lambda가 코드의.zip 파일 아카이브를 자동으로 생성
        - Lambda API, 명령줄 도구 또는 AWS SDK를 사용하여 함수를 생성하는 경우 배포 패키지를 생성해야 함.
        - 함수가 컴파일된 언어를 사용하거나 함수에 종속 항목을 추가하는 경우에도 배포 패키지를 생성해야 함.
    - 컨테이너 이미지
        - Docker 명령줄 인터페이스(CLI)와 같은 도구를 사용하여 코드 및 종속 항목을 컨테이너 이미지로 패키지화할
          수 있다. 그런 다음 Amazon Elastic Container Registry(Amazon ECR)에서 호스팅되는 컨테이너
          레지스트리에 이미지를 업로드할 수 있다.
- 함수 호출
    - 함수 URL 생성 및 관리
        - 함수 URL은 Lambda 함수를 위한 전용 HTTP(S) 엔드포인트이다.
        - 함수 URL 엔드포인트는 다음 형식을 취한다.
            - ```https://<url-id>.lambda-url.<region>.on.aws```
        - 함수 URL 생성(콘솔)
            - 함수 URL을 사용하여 새 함수를 생성하려면(콘솔)
                1. Lambda 콘솔의 함수 페이지를 연다.
                2. 함수 생성(Create function)을 선택
                3. 기본 정보에서 다음과 같이 한다.
                    1) 함수 이름(Function name)에 my-function과 같은 함수 이름을 입력
                    2) 런타임(Runtime)에서 원하는 언어 런타임을 선택합니다(예: Node.js 18.x).
                    3) 아키텍처(Architecture)에서 x86_64 또는 arm64를 선택
                    4) 권한(Permissions)을 확장한 다음, 새 실행 역할을 생성할지 아니면 기존 역할을 사용할지 여부를 선택
                4. 고급 설정(Advanced settings)을 확장한 다음 함수 URL(Function URL)을 선택
                5. 인증 유형(Auth type)에서 AWS_IAM 또는 NONE을 선택
                6. 함수 생성(Create function)을 선택
        - 함수 URL 생성(AWS CLI)
            - AWS Command Line Interface(AWS CLI)를 사용하여 기존 Lambda 함수에 대한 함수 URL을 생성하려면
              다음 명령을 실행
              ``` 
                 aws lambda create-function-url-config \
                   --function-name my-function \
                   --qualifier prod \ // optional
                   --auth-type AWS_IAM
                   --cors-config {AllowOrigins="https://example.com"} // optional
              ```
              이렇게 하면 함수 my-function에 대한 prod 한정자에 함수 URL이 추가됨

### CI / CD Tools
#### Github Actions
- GitHub Actions 정보
    - Github Actions의 이해
        - 개요
            - GitHub Actions는 빌드, 테스트 및 배포 파이프라인을 자동화할 수 있는 CI/CD(연속 통합 및 지속적인 업데이트) 플랫폼이다. 리포지
            토리에 대한 모든 끌어오기 요청을 빌드 및 테스트하거나 병합된 끌어오기 요청을 프로덕션에 배포하는 워크플로를 만들 수 있다.
        - GitHub Actions의 구성 요소
            - 워크플로
                - 워크플로는 하나 이상의 작업을 실행할 구성 가능한 자동화된 프로세스이다. 워크플로는 리포지토리에 체크 안된 YAML 파일에서 정의되며,
                리포지토리의 이벤트로 트리거될 때 실행되거나 수동으로 또는 정의된 일정에 따라 트리거될 수 있다.
                - 워크플로는 리포지토리의 .github/workflows 디렉터리에 정의된다. 리포지토리에 다음과 같은 각각의 다른 작업 집합을 수행하는 여러
                워크플로가 있을 수 있다.
                    - 끌어오기 요청을 빌드하고 테스트한다.
                    - 릴리스가 생성될 때마다 애플리케이션을 배포한다.
                    - 새 문제가 보고될 때마다 레이블을 추가한다.
                - 다른 워크플로 내에서 워크플로를 참조할 수 있다.
            - 이벤트
                - 이벤트는 워크플로 실행을 트리거하는 리포지토리의 특정 활동이다. 예를 들어 누군가가 끌어오기 요청을 만들거나, 이슈를 열거나, 리포지토리에
                커밋을 푸시할 때 GitHub에서 활동이 시작될 수 있다. 일정에 따라 REST API에 게시하여 또는 수동으로 워크플로를 트리거할 수 있다.
            - 작업
                - 작업은 동일한 실행기에서 실행되는 워크플로의 단계 집합이다.
                - 작업 간 종속성을 구성할 수 있다. 기본적으로 작업은 종속성이 없으며 병렬로 실행된다. 작업이 다른 작업에 종속되면 작업은 실행하기 전에 종속
                작업이 완료되기를 기다린다.
                - 예를 들어 작업 종속성 없이 서로 다른 아키텍처에 대한 여러 빌드 작업과 해당 빌드에 종속되는 패키징 작업을 구성할 수 있다. 빌드 작업은
                병렬로 실행되며, 모두 성공적으로 완료되면 패키징 작업이 실행된다.
            - actions
                - 작업은 복잡하지만 자주 반복되는 태스크를 수행하는 GitHub Actions 플랫폼용 사용자 지정 애프리에시션이다. 작업은 GitHub에서 Git 리포지
                토리를 가져오거나, 빌드 환경에 맞는 올바은 도구 체인을 설정하거나, 클라우드 공급자에 대한 인증을 설정할 수 있다.
            - 실행기
                - 실행기는 트리거될 때 워크플로를 실행하는 서버이다. 각 실행자는 한 번에 하나의 작업을 실행할 수 있다. GitHub는 워크플로를 실행할 Ubuntu Linux,
                Microsoft Windows, maxOS 실행기를 제공한다. 각 워크플로 실행은 새로 프로비저닝된 새 가상 머신에서 실행된다.
- 워크플로 작성
    - 빠른 시작
        - 첫 번째 워크플로 만들기
            1. Github 리포지토리의 .github/workflows 디렉터리에 github-actions-demo.yml이라는 워크플로 파일을 생성한다.
                - .github/workflows 디렉터리가 이미 있는 경우 Github에서 해당 디렉터리로 이동하고 파일 추가를 클릭한 다음 새 파일 만들기를 클릭하고
                파일 이름을 github-actions-demo.yml로 지정
            2. 다음 YAML 콘텐츠를 github-actions-demo.yml 파일에 복사한다.
                ```
                    name: GitHub Actions Demo
                    run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
                    on: [push]
                    jobs:
                    Explore-GitHub-Actions:
                        runs-on: ubuntu-latest
                        steps:
                        - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
                        - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
                        - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
                        - name: Check out repository code
                            uses: actions/checkout@v4
                        - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
                        - run: echo "🖥️ The workflow is now ready to test your code on the runner."
                        - name: List files in the repository
                            run: |
                            ls ${{ github.workspace }}
                        - run: echo "🍏 This job's status is ${{ job.status }}."
                ```
            3. 변경 내용 커밋을 클릭
            4. "변경 내용 제안" 대화 상자에서 기본 분기를 커밋하는 옵션이나 새 분기를 생성하고 pull request를 시작하는 옵션을 선택한다. 그런 다음 변경 내용 커밋
            또는 변경 내용 제안을 클릭한다.
    - 워크플로 정보
        - 워크플로 정보
            - 워크플로는 하나 이상의 작업을 실행할 구성 가능한 자동화된 프로세스이다. 워크플로는 리포지토리에 체크인된 YAML 파일에서 정의되며, 리포지토리의 이벤트로
            트리거될 때 실행되거나 수동으로 또는 정의된 일정에 따라 트리거될 수 있다.
            - 워크플로는 리포지토리의 .github/workflow 디렉터리에 정의된다. 리포지토리에 다음과 같은 각각의 다른 작업 집합을 수행하는 여러 워크플로가 있을 수 있다.
                - 끌어오기 요청을 빌드하고 테스트한다.
                - 릴리스가 생성될 때마다 애플리케이션을 배포한다,
                - 새 문제가 보고될 때마다 레이블을 추가한다.
        - 워크플로 기본 사항
            - 워크플로에는 다음과 같은 기본 구성 요소가 포함되어야 한다.
                1. 워크플로를 트리거하는 하나 이상의 이벤트
                2. 하나 이상의 _작업_이며, 각 작업은 실행기머신에서 실행되고 일련의 하나 이상의 _단계_를 실행한다.
                3. 각 단계에서는 워크플로를 간소화할 수 있는 재사용 가능한 확장인 작업을 정의하거나 실행하는 스크립트를 실행할 수 있다.
        - 워크플로 트리거

<hr />