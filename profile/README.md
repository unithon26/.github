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

문제와 솔루션을 **한 번** 입력하면, 같은 검증 가설에서 공개 랜딩과 카드뉴스 5장, 광고 문구와 Meta
광고가 나오고, 실제 방문·예약·Insights가 하나의 리포트로 돌아옵니다.

<table align="center">
  <tr>
    <td width="62%"><img src="https://raw.githubusercontent.com/unithon26/marketvalley/main/public/report/landing-page.png" alt="입력한 검증 기획으로 생성된 공개 랜딩 페이지" /></td>
    <td width="38%"><img src="https://raw.githubusercontent.com/unithon26/marketvalley/main/public/report/card-news.png" alt="같은 가설에서 생성된 Instagram 카드뉴스" /></td>
  </tr>
</table>

### 콘텐츠를 많이 만드는 제품이 아닙니다

없앤 건 고객을 만나기 전에 반복하던 일입니다. 채널마다 가치 제안을 다시 쓰고, 카드를 조판해 파일로
정리하고, 소재를 Ads Manager에 옮기고, 상태를 확인하고 여러 표의 반응을 취합하는 일. **시장성 판단과
고객 대화는 사람에게 남깁니다.** 사용자에게 남는 흐름은 `아이디어 입력 → 실제 반응 관찰 → 계속
검증할지 판단`뿐입니다.

### 브라우저를 닫아도 진행됩니다

```text
SUBMITTED → GENERATING → PREPARING → AWAITING_ACTIVATION
          → COLLECTING → FINALIZING → COMPLETED
```

Oracle worker가 Postgres lease 상태 머신을 이어서 처리합니다. 외부 API가 일시 실패하면 입력과 원래
단계를 보존한 채 재시도하고, 안전하게 복구할 수 없는 오류는 **성공으로 꾸미지 않습니다.**

### 돈이 나가는 경계

광고는 서버가 승인한 계정, 고정 lifetime 예산, 종료 시각이 모두 일치할 때만 활성화됩니다. 사용자별
광고와 예약자명단은 Google OAuth, HttpOnly 세션, Supabase RLS로 격리합니다. 리포트에 올라가는
숫자는 저장된 Meta Insights와 고유 방문, 동의 기반 예약뿐입니다. 임의로 만든 지표는 없습니다.
카드 미리보기와 ZIP, Meta 업로드는 같은 결정적 renderer를 씁니다.

### 만든 방식

`Next.js 16` `React 19` `Supabase` `PostgreSQL · RLS` `Anthropic Structured Outputs`
`Meta Marketing API` `Vercel` `Oracle Cloud` `Terraform`

CI에서 lint와 typecheck, 단위 테스트, production build, Chromium E2E, 비밀정보 비노출, Terraform과
container smoke를 검증합니다.

<p align="center">
  <sub>UNITHON 2026 · <strong>매니패스트 특별상</strong></sub>
</p>

<p align="center">
  <a href="https://github.com/ghdtjdwn">@ghdtjdwn</a> ·
  <a href="https://github.com/jisung1017">@jisung1017</a>
</p>
