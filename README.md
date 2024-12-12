# <!--<img src="Reports/우주타이거_로고.png" width="50px">--> 캡스톤디자인과창업프로젝트 18팀 우주타이거
### 주관적인 심리적 불편감을 겪는 20-30대를 위한 LLM기반 개인 맞춤형 챗봇 상담 서비스

[Client Repository 바로가기](https://github.com/TIME0227/Team18)
<br><br>

### ✏️ 사용 기술
<img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white"/></a>
<img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white"/></a>
<img src="https://img.shields.io/badge/OpenAI%20API-eee?style=for-the-badge&logo=openai&logoColor=412991"/></a>
<!--<img src="https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white"/></a>-->

### 🔧 주요 기능
Unity 클라이언트의 요청을 OpenAI API에 전달하고 응답을 다시 클라이언트에 반환한다. Unity 클라이언트와의 상호작용을 위해 POST 요청만 처리하도록 구현되었다.

<br>

## Source Codes
```
Team18-Server/
├── index.js            # Node.js 서버의 메인 파일
├── package.json        # 프로젝트의 메타데이터와 의존성 관리
├── package-lock.json   # 프로젝트의 메타데이터와 의존성 관리
└── vercel.json         # Vercel 플랫폼을 통한 서버 배포 관련 설정
```

<br>

## How to Build
다음은 클론한 리포지토리를 로컬 환경에서 빌드하는 방법이다.

1. **의존성 설치**
   ```
   npm install express body-parser cors dotenv openai
   ```
   
2. **.env 파일 작성**
  .env 파일을 생성하고 자신의 OpenAI API KEY를 작성한다.
   ```
   OPENAI_API_KEY='your-api-key'
   ```
4. **Node.js 서버 실행**
   ```
   node index.js
   ```
   `Proxy server running on http://localhost:PORT` 라는 메시지가 뜨면 서버가 성공적으로 실행 중이라는 의미이다.
   
<br>

## How to Test
다음은 서버 실행 후 curl을 사용하여 POST 요청을 테스트하는 명령어이다.
```
curl -X POST http://localhost:3000/chatgpt \
-H "Content-Type: application/json" \
-d '{
    "messages": [
        { "role": "system", "content": "You are a helpful assistant." },
        { "role": "user", "content": "Tell me a joke." }
    ]
}'
```
명령어를 실행하고 `{"response": "Sure! Here's one for you: \n\nWhy don't skeletons fight each other?\n\nThey don't have the guts."}` 와 같이 OpenAI 응답 형식으로 정상적으로 반환되는 것으로 테스트할 수 있다.
