---
title: "NotebookLM MCP 연결 메모"
updated: "2026-05-04"
doc_type: "ops-note"
status: "restored"
---

# NotebookLM MCP 연결 메모

이 문서는 VS Code/Codex에서 NotebookLM MCP 서버를 다시 연결하거나 점검할 때 참고하는 운영 메모이다.

## 현재 MCP 설정

설정 파일 위치:

- `C:\Users\jinmuk\AppData\Roaming\Code\User\mcp.json`

현재 등록된 서버:

```json
{
 "mcpServers": {
 "notebooklm": {
 "command": "C:\\Users\\jinmuk\\.local\\bin\\uv.exe",
 "args": [
 "run",
 "--with",
 "notebooklm-mcp-cli",
 "notebooklm-mcp"
 ],
 "env": {
 "UV_CACHE_DIR": "C:\\Users\\jinmuk\\Documents\\jinmuk\\.uv-cache",
 "NOTEBOOKLM_HL": "ko",
 "NOTEBOOKLM_QUERY_TIMEOUT": "180",
 "CONDA_NO_PLUGINS": "true"
 }
 }
 }
}
```

## 점검 절차

1. VS Code를 재시작하거나 MCP 서버를 다시 로드한다.
2. Codex 세션에서 NotebookLM 도구가 보이는지 확인한다.
3. 인증 문제가 있으면 `refresh_auth`를 먼저 시도한다.
4. 인증이 없거나 만료되었으면 `nlm login`으로 재인증한 뒤 다시 `refresh_auth`를 실행한다.
5. 대형 노트북 쿼리는 `notebook_query_start`와 `notebook_query_status`를 사용한다.

## 자주 쓰는 작업 흐름

### 기존 노트북 확인

- `notebook_list`
- `notebook_get`
- `notebook_describe`

### 기존 소스에 질문

- 소스가 이미 노트북 안에 있으면 `notebook_query`를 사용한다.
- 소스가 많아 타임아웃이 우려되면 `notebook_query_start`를 사용한다.

### 새 자료 찾기

- 웹/Drive에서 새 소스를 찾을 때는 `research_start`를 사용한다.
- 완료 후 `research_status`로 확인하고 `research_import`로 가져온다.

### 소스 추가

- URL: `source_add`의 `source_type: "url"`
- 텍스트: `source_add`의 `source_type: "text"`
- 로컬 파일: `source_add`의 `source_type: "file"`

## 주의

- NotebookLM MCP는 새 자료 검색과 기존 노트북 질의를 구분해서 써야 한다.
- `notebook_query`는 이미 노트북 안에 들어간 소스에 질문할 때 쓴다.
- 새로운 웹 자료를 찾는 작업은 `research_start`가 맞다.
- 대량 정리 작업 전에 결과 파일을 바로 삭제하지 말고, 먼저 후보 목록을 만들어 검토한다.

## 연관된 생각
- [[소스 전수 분석 프롬프트 가이드]] | 같은 문제 영역에서 함께 읽을 수 있는 인접 개념이다.
- [[에버그린 노트 공통 작성 가이드]] | 같은 문제 영역에서 함께 읽을 수 있는 인접 개념이다.

