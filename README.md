# marknote-gemini

Antigravity, Antigravity CLI, Antigravity IDE 의 사용법을 정리하는 문서입니다. 초창기에는 Gemini CLI 에 대한 문서를 다루었는데 해당 내용은 [gemini-cli](./gemini-cli) 에 있습니다. Gemini CLI 가 Antigravity CLI 로 통합되면서 Gemini CLI 버전으로 작성했던 문서는 Antigravity CLI 버전으로 새로운 문서들을 만들 예정입니다.<br/>

Gemini 의 컨텍스트 최대 허용치는 2M토큰 (200만 토큰)이라고 합니다. Anthropic, Open AI 의 컨텍스트 용량을 비교해보면 다음과 같은데 Gemini 의 컨텍스트 용량이 월등히 높습니다. 

| 모델 / 개발사 | 컨텍스트 창 (Context Window) | 실제 텍스트 분량 기준 |
| :--- | :--- | :--- |
| **Google Gemini 1.5 Pro** | **2,000,000 토큰 (2M)** | 책 약 30~40권, 코드 수십만 라인 |
| **Anthropic Claude 3.5 Sonnet** | **200,000 토큰 (200K)** | 책 약 3~4권 내외 |
| **OpenAI GPT-4o** | **128,000 토큰 (128K)** | 책 약 1~2권 내외 |

<br/>

원래는 Claude Code 를 공부하다가 Gemini CLI 버전으로 바꿔서 학습하는걸 해오다가 위의 표처럼 Gemini CLI 에 가격 대비 효율이 좋다는 장점을 찾기도 했고, Claude 의 `Claude.md` 를 재귀적으로 찾는 방식이나 컨텍스트 낭비하는 구조 등을 보면서 Gemini CLI 를 공식문서를 하나씩 번역을 하면서 Gemini CLI 도 Claude Code 에 비견될 정도로 좋은 기능을 많이 제공하고 있다는 사실을 알게 됐습니다.<br/>

그래서 이 문서 저장소에 Gemini CLI 관련 내용들을 번역해두었는데, 몇일 전 쯤 (2026년 5월 23일쯤) Antigravity 2.0 이 출시되면서 Antigravity 의 기능이 Antigravity IDE, Antigravity CLI, Antigarvity, Antigravity SDK 로 나뉘면서 더 많은 좋은 기능들이 제공되게 되어서 Antigravity 관련 제품들도 정리해두기로 했습니다.<br/>
<br/>

Meta AI 도 좋은 기능을 많이 제공하기 시작한다면, 그때는 Meta AI 도 별도의 문서 저장소에 정리하게 되지 않을까 싶습니다. 둘다 결제해서 쓸듯 싶습니다. Meta AI 도 워낙 업계 수준급 엔지니어들이 영입되어서 개발한 것이기에 좋은 기능들이 많이 있을 것 같아서 아마도 Meta AI 가 다국어 지원을 시작한다면... 아마도 그때는 Meta AI 도구도 많이 쓰게 될 듯할것 같고 문서정리를 하게 되지 않을까 싶습니다.<br/>
<br/>


Meta, Google 모두 Infra 쪽으로는 비용감당이 되거나, 그만한 데이터 센터를 가지고 있는 벤더 급이어서 가격을 더 싸게 소비자에게 좋은 기능을 계속 제공하게 될 것 같아서 .... 잡설이 길었네요.
