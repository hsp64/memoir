# 📝 2025-08-10 일일 회고 - 박현수

## 🌱 오늘의 작업 내용
- 테스트 환경에서 DB 자동 연결 방지를 위해  
  `@SpringBootApplication(exclude = { DataSourceAutoConfiguration.class, HibernateJpaAutoConfiguration.class })` 설정 적용 및 검증
- `templates` 내 단일 HTML 파일을 `static/js`, `static/css`로 분리하여 리소스 구조 개선  
  → 페이지별 스크립트/스타일 연결 확인 완료
- `PageTestController` 동작 점검 및 호스트/참여자 전용 게시판 라우팅/권한 구조 확인  
  → 추후 URL/권한 정책 재설계 예정
- DDL 최종본 오타 수정 및 스키마 구조 재확인

---

## 🤔 오늘의 고민 / 느낀 점
- 테스트 환경에서 DB 연결이 불필요하게 시도되는 문제는 테스트 프로파일 분리로 해결할 수 있었으나,  
  통합 테스트 환경에선 별도의 데이터소스 전략(Flyway/Testcontainers)이 필요할 것 같음
- HTML/CSS/JS 구조를 분리하니 유지보수성과 가독성이 확실히 좋아졌지만,  
  링크 경로 관리가 중요하다는 점을 다시 느꼈음


---

## 📅 내일 할 일
- 분리된 게시판(소통용) 미팅페이지와 연결
- 게시판 및 참여자 리스트 개발 시작

---
