# 🔥 Assignment_REDBRICK (with NestJS)

이 Read.me에는 제가 무엇을 했는지만 적혀있습니다. 팀 전체가 무엇을 했는지 궁금하시다면 하단의 링크를 참조해주세요.    
[Assignment_2_MAPIA 팀 Repository](https://github.com/preOnboarding-Team13/Assignment_2_MAPIA)

<br/>

<br>

## 🍭 TIL 블로그 주소

- 원동균 : [티스토리 블로그](https://tristy.tistory.com/45)

<br>

## 🌎 배포

주소 : http://3.144.245.28:3000

<br>

## 🛠 프로젝트 빌드 및 서버 실행 방법

1. 상단의 Code 버튼을 눌러 경로를 복사한 후 클론 받습니다.

```
$ git clone https://github.com/preOnboarding-Team13/Assignment-3-redbrick.git
```

2. 패키지를 설치합니다.

```
$ npm install
```

3. 서버를 실행해 줍니다.

```
$ npm start
```

4. 정해진 API에 접근하여 서비스를 이용합니다.

<br>

## 📝 과제 요구사항

### [필수 포함 사항]

-   READ.ME 작성
    - 프로젝트 빌드, 자세한 실행 방법 명시
    - 구현 방법과 이유에 대한 간략한 설명
    - 완료된 시스템이 배포된 서버의 주소
    - Swagger나 Postman을 통한 API 테스트할때 필요한 상세 방법
    - 해당 과제를 진행하면서 회고 내용 블로그 포스팅
-   Swagger나 Postman을 이용하여 API 테스트 가능하도록 구현
-   선호 기술 : Javascript (+TypeScript)

### [과제 안내]

위즈랩은 학생들이 코딩에 재미를 느낄 수 있도록 간단한 게임을 코딩을 통해 만들 수 있는 플랫폼입니다

게임을 만들기 위해선 다음과 같은 과정이 필요합니다

1. 회원가입
2. 게임 제작하기 - 제작 중 단계의 게임을 '프로젝트'라고 합니다
3. 게임 출시(퍼블리싱)하기

각 단계의 요구사항은 다음과 같습니다

- 회원가입
- 게임 제작
  - 프로젝트는 **'실시간'**으로 반영이 되어야 합니다
    - 예를 들어, 프로젝트 수정 중 의도치 않은 사이트 종료 시에도 **작업 내역은 보존**되어야 합니다
- 게임 출시하기
  - **프로젝트 당 퍼블리싱 할 수 있는 개수는 하나**입니다. 퍼블리싱한 게임은 수정할 수 있어야 하며, 수정 후 재출시시 기존에 퍼블리싱된 게임도 수정됩니다
  - 출시하는 게임은 다른 사용자들도 볼 수 있으며, 사용자들의 **조회수 / 좋아요 등을 기록**할 수 있어야 합니다
  - '게임 혹은 사용자 **검색**'을 통해서 찾을 수 있어야 합니다

**아래의 문제를 풀어야 합니다**

```jsx
- 참고 - 문제 1,2번은 필수 문제이며, 3번은 선택입니다
문제 1. '회원가입'부터 '게임 출시'까지 필요한 테이블을 설계하세요

문제 2. 다음에 필요한 API를 설계하세요

	1. 게임 제작하기에 필요한 API
	3. 조회수 수정, 좋아요 API
	4. 게임 혹은 사용자로 검색 API

- option -
문제 3. 
 (1) 프로젝트 실시간 반영을 위한 Architecture를 설계하세요 ( 그림이 있다면 좋습니다 )
 (2) 위의 Architecture를 토대로 기능을 구현하세요
```

<br>

## 🏫 사용 기술

-   Backend : <img src="https://img.shields.io/badge/NestJS-E0234E?style=flat&logo=NestJS&logoColor=white"/></a> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=TypeScript&logoColor=white"/></a> 
-   DataBase : <img src="https://img.shields.io/badge/MongoDB-008CC1?style=flat&logo=MongoDB&logoColor=white"/></a>
-   Collaboration : <img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=Git&logoColor=white"/></a> <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=GitHub&logoColor=white"/></a> <img src="https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=Postman&logoColor=white"/></a>
-   Deploy: <img src="https://img.shields.io/badge/Amazon AWS-232F3E?style=flat&logo=Amazon AWS&logoColor=white"/>

<br>

## 📂 폴더 구조

6개의 domain을 생성했습니다.

- socket
- project
- game
- auth
- user
- game

database 폴더: mongoDB 연결 폴더

entities 폴더: mongoose Schema 폴더

test 폴더: e2e test 폴더

```
.
├── src
│  ├── database
│  │  │  ├── database.module.ts
│  │  │  └── database.provider.ts
│  ├── domain
│  │  ├── auth
│  │  │  ├── guards
│  │  │  │  ├── createProject.dto.ts
│  │  │  │  └── createProject.dto.ts
│  │  │  ├── auth.controller.spec.ts
│  │  │  ├── auth.controller.ts
│  │  │  ├── auth.module.ts
│  │  │  ├── auth.service.spec.ts
│  │  │  └── auth.service.ts
│  │  ├── project
│  │  │  ├── dto
│  │  │  │  └── createProject.dto.ts
│  │  │  ├── exception
│  │  │  │  └── NotFoundGameException.dto.ts
│  │  │  ├── project.controller.spec.ts
│  │  │  ├── project.controller.ts
│  │  │  ├── project.module.ts
│  │  │  ├── project.controller.ts
│  │  │  ├── project.service.spec.ts
│  │  │  └── project.service.ts
│  │  ├── game
│  │  │  └── ...
│  │  ├── project
│  │  │  └── ...
│  │  ├── user
│  │  │  ├── exception
│  │  │  │  ├── DuplicatedUserException.dto.ts
│  │  │  │  ├── NotFoundUserException.dto.ts
│  │  │  │  └── UnauthorizedUserException.dto.ts
│  │  │  └── ...
│  │  ├── like
│  │  │  ├── like.controller.spec.ts
│  │  │  ├── like.controller.ts
│  │  │  ├── like.module.ts
│  │  │  ├── like.service.spec.ts
│  │  │  └── like.service.ts
│  │  ├── socket
│  │  │  ├── socket.gateway.spec.ts
│  │  │  ├── socket.gateway.ts
│  │  │  └── socket.module.ts
│  ├── entities
│  │  ├── block.schema.ts
│  │  ├── game.schema.ts
│  │  ├── project.schema.ts
│  │  ├── scene.schema.ts
│  │  ├── sprite.schema.ts
│  │  └── user.schema.ts
│  ├── global
│  │  ├── common
│  │  │  ├── CommonResponse.ts
│  │  │  ├── ErrorCode.ts
│  │  │  ├── ErrorResponse.ts
│  │  │  ├── SuccessCode.ts
│  │  │  └── SuccessResponse.ts
│  │  ├── exception
│  │  │  └── ExceptionHandler.ts
│  ├── app.module.ts
│  ├── main.ts
├── test
│  ├── app.e2e-spec.ts
│  └── jest-e2e.json
├── .env
├── nest-cli.json
├── package.json
├── package-lock.json
├── tsconfig.json
├── tsconfig.build.json
└── README.md
```

<br>


## 🧬 DB 모델링

![Untitled Diagram drawio (2)](https://user-images.githubusercontent.com/43634786/140792086-063c5ac0-49cc-4adf-a963-1d8015bee08e.png)

<br>


# 🔗 구현 기능

### Check List


- 회원가입

	✅ 회원을 생성하는 API
	
	✅ 로그인 API

- 프로젝트

	✅ 프로젝트 생성 API
	
	✅ 선택한 프로젝트를 가져오는 API
	
	✅ 프로젝트 편집 API
	
	✅ 프로젝트 조회 API
	
	✅ 프로젝트 삭제 API

- 게임

	✅ 해당 프로젝트를 퍼블리싱 하는 API
	
	✅ 퍼블리싱된 게임을 검색하는 API

- 좋아요 / 싫어요

	✅ 좋아요 API
	
	✅ 싫어요 API
	
	✅ 선택한 게임 데이터를 가져오고, 조회수를 증가시키는 API


- 기업이 제시한 문제

	✅ 회원가입 ~ 게임 출시까지 필요한 테이블 설계
	
	✅ 게임 제작하기에 필요한 API
	
	✅ 조회수 수정, 좋아요 API
	
	✅ 게임 혹은 사용자로 검색 API
	
	✅ 프로젝트 실시간 반영을 위한 Architecture 설계
	
	✅ 설계한 Architecture를 토대로 기능 구현
	
	✅ E2E Test
	
	✅ Unit Test 

<br/>
<br/>

🧪 내가 이번 프로젝트에서 무엇을 했지?
-----------------  

**1) 해당 기업의 홈페이지 분석 및 socket 설정**  

이번 과제에서는 특이하게도 실시간으로 반영이 되어야 한다는 조건이 붙어있었습니다. 직접 해당 기업의 사이트에 회원가입을 하고 서비스를 이용해보니까 요구사항에 왜 이런 항목이 있었는지 알 수 있었습니다. 열심히 게임을 만들다가 잘못해서 인터넷이 종료된 경우, 작업물이 날라가면 안되니까요. 그래서 이 부분을 어떻게 처리하고 있는지 `Chrome`의 `개발자 도구`를 통해서 확인해본 결과 게임 제작 서비스를 이용하고 있을 경우, 사용자가 오브젝트를 배치할 때마다 소켓 통신을 통해서 데이터를 저장한다는 것을 확인할 수 있었습니다. 그래서 저희 팀은 소켓을 사용하여 프로젝트를 실시간으로 저장할 수 있게끔 구현하기로 했습니다.

<br/>

<p align="center"><img src="https://user-images.githubusercontent.com/52685665/140965390-6260cab4-8f34-4b95-8d16-85060505b9c2.png"></p>

<br/>
<br/>

저희는 project라는 url을 설정하고 해당 소켓에 연결하도록 구현하였고, update 요청을 할 때마다 project 전체 데이터를 전송하여 한번에 업데이트 하는 방식을 선택하였습니다. 아무래도 사용자가 실시간으로 블럭, 씬, 프로젝트를 수정할 수 있기 때문에 분리해서 구현하는 것 보다 한번에 데이터를 업데이트 시키는 것이 좋다고 판단하였습니다.  

<br/>

```javascript
@WebSocketGateway({ namespace: "project" })
export class SocketGateway {
	constructor(
		@InjectModel(Project.name) private project: Model<ProjectDocument>
	) {}

	@SubscribeMessage("update")
	handleMessage(@MessageBody() data) {
		return this.project
			.findOneAndUpdate({ projectId: data.projectId }, data, {
				returnOriginal: false
			})
			.exec();
	}

	handleDisconnect(client: Socket) {
		console.log(`Client disconnected: ${client.id}`);
	}

	handleConnection(client: Socket) {
		console.log(`Client Connected: ${client.id}`);
	}
}
```

<br/>
<br/>

Postman으로는 다음과 같이 소켓 통신 테스트를 진행할 수 있었습니다.  

<br/>

<p align="center"><img src="https://user-images.githubusercontent.com/52685665/140968082-e8db02d9-52f5-4a4f-aeba-641251b06a2d.png"></p>

<br/>
<br/>

**2) `좋아요`, `싫어요` 기능 구현 및 unit Test**  

좋아요와 싫어요 모두 로그인한 사용자만 가능하며, 사용자당 한번 씩만 할 수 있는 기능입니다. 퍼블리싱한 게임을 대상으로는 딱 하나만 좋아요를 누르거나 그것을 취소할 수 있는것이죠. 따라서 저는 Project 컬렉션에 해당 좋아요 수 부분을 리스트로 저장하며, 좋아요를 누른 경우에는 `해당 ID : true`, 싫어요를 누른 경우에는 `해당 ID:false`를 주기로 했습니다. 이렇게 하면 나중에 좋아요 수를 구하기도 쉽고, 클라이언트에 해당 사용자가 다음에 어떤 버튼을 누를 수 있게 해야하는지를 알려줄 수 있습니다. 다만 여기서 아쉬웠던 것은 service 코드에 에러처리와 비교문 등이 얽혀있어서 가독성이 좋지 않다는 점입니다. 이때 시간이 없어서 이 부분을 고치지 못했지만, 이렇게 짜면 가독성이 좋지 않다는 것을 느끼고 이후 프로젝트에서는 서비스에서 데이터베이스에 접근하는 것이 아닌 리포지토리에서 접근하도록 바꿨습니다.

<br/>

<p align="center"><img src="https://user-images.githubusercontent.com/52685665/144447110-a00308f6-a6c0-44f5-87d6-94dd1d503c6c.png"></p>

<br/>

Unit Test는 Jest를 사용하여 진행했으며, 요번에는 성공했을 때의 테스트 뿐만아니라 실패했을 경우도 테스트를 하였습니다. 

<br/>

<p align="center"><img src="https://user-images.githubusercontent.com/52685665/144447775-f5f91a9f-9f3d-4af3-833c-34b1aa639694.png"></p>

<br/>

## 😎 Architecture

<p align="center"><img src="https://user-images.githubusercontent.com/52685665/140969833-e8c664a3-5166-48fe-bbee-c5d53fbf938d.png"></p>

<br/>

## 해당 프로젝트에서 간과한 부분

저희처럼 MongoDB 데이터를 다루면 아래의 사진처럼 Maximum Call Stack Error가 발생합니다. 처음 구현할 때는 아무문제 없어 보였으나, 각자 작업한 부분을 합치고 각종 데이터들을 가져오면서 MongoDB에서 문제가 발생하게 되었습니다. 해당 문제를 프로젝트 제출 직전에 발견하여서 수정은 하지 못하였습니다. 하지만 해당 문제는 가져오는 데이터끼리 서로 참조하기 때문에 발생하는 것이었고, 이는 mongoose Entity의 관계 설정 문제이기 때문에 Entity 설정을 수정하고 그에 맞춰 코드를 수정하면 해당 오류는 해결할 수 있을 것 같습니다.

<p align="center"><img src="https://user-images.githubusercontent.com/52685665/140994654-a17bb159-2caf-401a-aad3-355decd165b4.png"></p>

<br/>

## 🐾 API 

[Postman 주소-링크](https://documenter.getpostman.com/view/15410333/UVC5F82o)

<br/>

## 🐾 API Test 방법

#### 1. 위의 Postman 주소 링크를 클릭하여 Postman으로 들어갑니다.
#### 2. 서버 주소가 알맞은지 확인합니다.

![image](https://user-images.githubusercontent.com/41619081/140978000-325a85ce-e0ae-4f26-9e6a-980e382b58f1.png)

#### 3. Signup, Login API를 이용하여 회원가입과 로그인을 진행할 수 있습니다.

![image](https://user-images.githubusercontent.com/41619081/140990609-120571c6-ae78-4569-b921-c85b40bed2dc.png)

#### 4. Project Create, Read, Edit, Delete API를 이용하여 유저는 각각의 게임 프로젝트를 생성, 상세보기, 편집, 삭제가 가능합니다.

![image](https://user-images.githubusercontent.com/41619081/140990936-c8d6428e-01c4-44a6-90c3-fb374188edfa.png)
![image](https://user-images.githubusercontent.com/41619081/140987859-268e63b8-a99d-4af0-a101-34a3098a017c.png)

#### 5. Game API를 이용하여 해당 게임을 만든 유저는 퍼블리싱 할 수 있고, 퍼블리싱 된 게임 1개를 볼 수 있습니다.

![image](https://user-images.githubusercontent.com/41619081/140991425-8102815d-672c-440e-ab8a-c27e3926a46d.png)

#### 6. Like, Hate API를 이용하여 로그인 한 유저는 퍼블리싱 된 게임에 좋아요와 싫어요를 누를 수 있습니다.



