# kjknews — 외부 예약 실행 전용 저장소

이 저장소는 KJKNEWS(https://www.kjknews.com) 사이트의 **예약 작업 호출만** 담당합니다. 사이트 소스 코드는 들어 있지 않습니다.

- `.github/workflows/kjknews-cron.yml`: 5분마다 `https://www.kjknews.com/api/cron/tick` 호출
  - 박영광 기자 자동 기사 (매일 06·12·19시 KST, 회차당 3건)
  - 언론사 피드 수집 · SEO 점검 · 여론광장 갱신 · R2 기사 백업
- 서버가 50초 간격 제한과 회차 잠금을 걸어 두어, 여러 번 호출해도 기사가 중복 작성되지 않습니다.
- 매월 1일 keepalive 커밋으로 GitHub의 "60일 비활성 시 예약 중지"를 방지합니다.
- 수동 실행: Actions → kjknews-cron → Run workflow
