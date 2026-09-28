# 에사(ASR)

[English](README.md) · [日本語](README.ja.md)

에사(ASR)는 여러 AI 도구가 함께 쓰는 기억 저장소입니다. 원격 MCP 서버로 운영합니다. 한 도구에서 남긴 결정을 다른 도구에서 원문 그대로 찾습니다.

이 저장소에는 문서, 에이전트 지침, 예시가 있습니다. 서버 소스는 공개하지 않습니다.

- 웹사이트: https://asrmemory.com
- MCP 주소: `https://asrmemory.com/mcp` (Streamable HTTP, OAuth 2.1)
- 공식 MCP Registry: `com.asrmemory/asr`

## 연결 3단계

1. AI 도구의 원격 MCP 서버(커스텀 커넥터) 설정에 `https://asrmemory.com/mcp` 를 넣습니다.
2. 로그인 화면이 뜨면 이메일, Google, 카카오, GitHub 중 하나로 로그인합니다. 키를 복사할 필요가 없습니다.
3. "에사에 기억해: 결제는 Postgres로 하기로 했어"라고 말합니다. 다른 도구에서 "결제 DB 뭐로 정했지?"라고 물어봅니다.

로그인 화면을 열 수 없는 도구는 대시보드(https://asrmemory.com/app/)에서 발급한 API 키로 연결합니다. 도구별 안내: https://asrmemory.com/docs.html

가입 없이 프로젝트 화면(마당)을 보려면 예시 화면을 여세요: https://asrmemory.com/madang/?demo

## 도구와 지침

도구 22개의 목록은 [README.md](README.md#tools-22)에 있습니다. 에이전트 지침은 [AGENTS.ko.md](AGENTS.ko.md)입니다. `CLAUDE.md`, `AGENTS.md`, `GEMINI.md`에 붙여 넣어 씁니다. 에사 없이도 쓸 수 있습니다.

## 데이터

- 계정마다 기억 공간이 따로 있습니다. 배포할 때마다 계정 간 접근 시험을 돌리고, 하나라도 실패하면 배포를 멈춥니다.
- 지운 기억은 먼저 휴지통으로 가고 되살릴 수 있습니다. 영구 삭제는 따로 요청해야 합니다.
- `memory_export`로 전부 내보내고, 대시보드에서 계정을 지울 수 있습니다.
- 데이터가 어디로 가는지: https://asrmemory.com/privacy.html
- 비밀번호, 키, 아이들 대화는 일반 기억으로 저장하지 마세요. 민감한 값은 `secret_save`를 씁니다.

## 가격

베타 기간 무료, 계정당 기억 1,000건까지입니다. 찾기, 떠올리기, 내보내기는 건수에 세지 않습니다. `asr_tidy`로 남긴 정리본도 한도에 넣지 않습니다.

## 의견

이 저장소에 이슈를 남기거나 idoweddings@naver.com으로 보내 주세요.

## 라이선스

문서와 에이전트 지침: CC BY 4.0. `examples/`의 예시 코드: MIT. [LICENSE](LICENSE)를 보세요.
