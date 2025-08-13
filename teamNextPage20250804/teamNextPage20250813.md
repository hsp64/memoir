## 📅 오늘의 회고록

### 1. 오늘 한 일

* **게시판 기능 개발**

  * Domain & Repository → Service → DTO → Controller까지 구현 완료 (테스트 제외).
  * `@Controller` 기반으로 API 엔드포인트 작성 및 `@ResponseBody` 추가.
  * 게시글·댓글 작성, 수정, 삭제에 대한 **권한 검증 로직** 적용.
  * 페이징 조회 API 작성 시 RESTful 원칙 준수(경로 + 쿼리 파라미터 활용).
  * 예외 처리: `CustomException` + `GlobalExceptionHandler`로 통합.
  * Repository 및 Service 레이어에서 username 기반 데이터 매핑 구현.

---

### 2. 개발 주요 포인트

* **권한 관리**

  * HOST 또는 APPROVED 상태의 참여자만 게시글·댓글 작성 가능.
  * 작성자 본인 또는 HOST만 수정·삭제 가능.
* **데이터 정합성**

  * FK 제약 없음 → 게시글 삭제 시 댓글 수동 삭제.
  * 트랜잭션으로 데이터 일관성 보장.
* **페이징 조회**

  * 경로에는 meetingId, 쿼리 파라미터로 page·size 적용.
* **예외 처리**

  * Service → `CustomException` 던짐.
  * Entity → `IllegalArgumentException` 던짐, Service에서 변환.
  * `GlobalExceptionHandler`에서 일괄 처리.

---

### 3. 배운 점

* RESTful API 설계 시 페이징 파라미터를 경로가 아닌 **쿼리 파라미터로 두는 이유**.
* Entity와 Service에서 예외를 나눠 쓰는 이유(계층별 책임 분리).
* JavaDoc의 `@throws`는 문서화를 위한 것이고, 실제 예외는 GlobalExceptionHandler에서 처리한다는 점.
* Repository에서 다수의 사용자 정보를 한 번에 조회해 Map으로 변환하는 방식.

---

### 4. 어려웠던 점

* `User::getUserId`, `User::getUsername` 메서드 사용 시 User 엔티티의 실제 필드명·Getter 불일치 문제.
* `@RestController` → `@Controller` 변경 시 모든 메서드에 `@ResponseBody` 추가 필요.
* DTO와 Response 매핑에서 username 필드 일관성 유지.

---

### 5. 해결 방법

* User 엔티티 필드명에 맞게 `User::getId`, `User::getUsername` 등으로 수정.
* Controller 전환 시 import 및 `@ResponseBody` 명시로 문제 해결.
* DTO 변환 시 Service에서 username을 매핑 후 전달하도록 구조 변경.

---

### 6. 내일 할 일

* Service, Controller 단위 테스트 작성.
* JWT 인증 적용 (`@RequestAttribute("userId")` 부분 인터셉터 연동).
* 사용자 조회 로직 최적화 (N+1 문제 방지).
* API 명세서 최신화.
