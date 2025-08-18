## 2025-08-16 (토) — **댓글/참여 신청·승인·거절, 권한/상태 전이 고도화**

### 1) 오늘 한 일 요약

* **댓글 CRUD** 구현 및 게시판과 통합.
* **참여 신청 버튼(로그인 사용자)**, **호스트 전용 수락/거절 버튼** 동작 연결.

### 2) 백엔드 진행

* **DTO**: `CommentCreateRequest/Response`, `CommentUpdateRequest/Response`.
* **Participant 흐름**

  * `ParticipantDecisionRequest/Response`, `ParticipantResponse`.
  * `MeetingParticipantRepository`에 승인/거절/존재 확인용 쿼리 구성.
* **Service**

  * 신청(중복 신청 방지), 승인/거절 시 상태 전이(예: `PENDING → APPROVED/REJECTED`) 트랜잭션 처리.
  * 게시판 접근 권한: HOST 또는 APPROVED만 작성 가능 검증.
* **Controller**

  * `/api/meetings/{id}/comments`, `/api/meetings/{id}/participants` 관련 엔드포인트 정리.

### 3) 프론트엔드 진행

* **UI/JS**

  * 로그인 시에만 **참여 신청** 노출, 이미 신청/승인 상태면 비활성 처리.
  * HOST에게만 **승인/거절** 버튼 노출, 클릭 시 서버에 상태 변경 요청 → 화면 즉시 반영.
  * 댓글 작성/수정/삭제 시 낙관적 업데이트 후 실패 시 롤백 처리.

### 4) 트러블슈팅

* **권한 경로 오류**: 연관 경로 명시(`meeting.id`, `participant.id`)로 파생쿼리 안정화.
* **테스트 이슈**: Repository 메서드 시그니처/네이밍 조정, AssertJ 타입 팩토리 사용 오류 정정.

### 5) 리팩토링 포인트

* 상태 전이는 **서비스 메서드 단일 책임**으로 묶고 이벤트성 로깅 추가.
* 참가자/게시판 권한 체크 공통 유틸로 분리.

### 6) 배운 점/인사이트

* 권한/상태 로직은 **UI 노출 제어 + 서버 강제 검증**의 이중 구조가 안전하다.

### 7) 내일 할 일

* 상세 전체 수정 플로우(모임 정보 수정), 이미지 등 부가 필드 정리.
* 에러 응답 규격 통일, 프론트 에러 핸들링 공통화.

