<p align="center">
  <img src="./assets/marketvalley-cover.svg" width="100%" alt="marketvalley — UNITHON 2026 매니패스트 특별상" />
</p>

<p align="center">
  <a href="https://marketvaley.vercel.app"><strong>서비스 »</strong></a>
</p>

<p align="center">
  <a href="https://github.com/unithon26/marketvalley">소스 코드</a> ·
  <a href="https://github.com/unithon26/marketvalley/blob/main/docs/demo-runbook.md">데모 실행서</a> ·
  <a href="https://github.com/unithon26/marketvalley/blob/main/docs/validation.md">검증 기록</a> ·
  <a href="https://github.com/unithon26/marketvalley/actions/workflows/ci.yml">CI</a>
</p>

---

marketvalley는 첫 시장 반응을 확인하려는 예비창업가와 1인 사업자를 위한 자동 시장검증
서비스입니다. 문제 배경과 솔루션을 **한 번** 입력하면 같은 검증 가설에서 공개 랜딩과
Instagram 카드뉴스, 광고 문구와 Meta 광고를 만들고, 실제 방문·예약·Insights를 하나의
리포트로 돌려줍니다.

<table align="center">
  <tr>
    <td width="62%"><img src="https://raw.githubusercontent.com/unithon26/marketvalley/main/public/report/landing-page.png" alt="입력한 검증 기획으로 생성된 공개 랜딩 페이지" /></td>
    <td width="38%"><img src="https://raw.githubusercontent.com/unithon26/marketvalley/main/public/report/card-news.png" alt="같은 가설에서 생성된 Instagram 카드뉴스" /></td>
  </tr>
  <tr>
    <td align="center"><sub>생성된 공개 랜딩 페이지</sub></td>
    <td align="center"><sub>같은 가설에서 나온 카드뉴스</sub></td>
  </tr>
</table>

> UNITHON 2026 매니패스트 특별상 공식 수상

더 많은 콘텐츠를 빠르게 만드는 제품이 아닙니다. 고객을 만나기 전에 반복하던 채널별 재작성과
조판, 파일 정리, 광고 등록, 상태 확인과 데이터 취합을 없애고 **시장성 판단과 고객 대화는 사람에게
남깁니다**. 사용자에게 남는 흐름은 `아이디어 입력 → 실제 반응 관찰 → 계속 검증할지 판단`입니다.

### 브라우저를 닫아도 진행됩니다

```text
SUBMITTED → GENERATING → PREPARING → AWAITING_ACTIVATION
          → COLLECTING → FINALIZING → COMPLETED
```

Oracle worker가 Postgres lease 상태 머신을 이어서 처리합니다. 외부 API가 일시 실패하면 입력과
원래 단계를 보존한 채 재시도하고, 안전하게 복구할 수 없는 오류는 **성공으로 꾸미지 않습니다.**

### 신뢰할 수 있는 제품 경계

- Google OAuth, HttpOnly 세션과 Supabase RLS로 사용자별 광고·예약자명단을 격리합니다.
- 서버가 승인한 광고계정, 고정 lifetime 예산과 종료 시각이 일치할 때만 광고를 활성화합니다.
- 카드 미리보기와 ZIP, Meta 업로드는 같은 결정적 renderer를 사용합니다.
- 임의 지표 대신 저장된 Meta Insights, 고유 방문과 동의 기반 예약만 표시합니다.

Next.js 16과 React 19, Supabase Auth·PostgreSQL·RLS, Anthropic Structured Outputs,
Meta Marketing API·Insights로 만들고 Vercel과 Oracle Cloud에 배포합니다. CI에서 lint와
typecheck, 단위 테스트, production build, Chromium E2E, 비밀정보 비노출, Terraform과
container smoke를 검증합니다.

2026년 8월 24일부터 26일까지 열린 UNITHON 2026에서 숭실대학교 학생 팀이 만들었습니다 —
[@ghdtjdwn](https://github.com/ghdtjdwn) ·
[@jisung1017](https://github.com/jisung1017)

<p align="center">
  <a href="https://marketvaley.vercel.app"><strong>marketvalley 직접 사용해 보기 →</strong></a>
</p>
