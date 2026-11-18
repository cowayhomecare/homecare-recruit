# Recruitment update — 2026-11-18

Production: https://recruit.cowayhc.kr/
Code commit: 00a40b5273309ae08d5ee8c85d8b8aab4155ca0a
Rollback branch: backup/recruit-before-20261118 (0d74c1727f165a3b3d8df0f891615765577df672)

## Scope
Only root index.html changed. No food/blackfriday, other repositories or Cloudflare edits.
- First screen explicitly names Kimhae Coway Homecare Doctor; retains commission-only, consignment-contract and sales disclosures.
- Removed repeated fit/FAQ content; income explanation immediately follows work; conditions reduced to three items.
- Name, phone, car and required consent are mandatory. Birth year/address removed; optional memo remains collapsed with explicit conditional consent.
- Restores existing server-supported formVersion=3, consentVersion=2026-11-simple-v1; existing POST endpoint unchanged. Do not invent birth years to satisfy v4.
- Field-specific accessible errors; first invalid field receives focus. Fixed mobile CTA hides when the form intersects viewport. Secondary fixed CTA uses existing SMS, phone retained in contact area.
- Removed unresolved work-note footer; existing corporate details retained, contact named Jo Youngsik. This does not constitute independent legal verification of corporate/operator status.

## Validation
- node --check passed; git diff --check passed.
- Existing stored Apps Script validate_ accepted v3 with no birthYear/address and rejected missing consent/car, unconsented memo.
- Browser: empty-form and memo-consent errors verified, privacy content matches fields; 390px iframe mobile layout reviewed, CTA hides at form.
- Real v3 POST submitted with identifiable test name 테스트조영식 using owner's published business number. Google response: 지원서가 잘 도착했어요.
- Native Sheets read verified test in 지원자접수 row 6 at 26.11.18 14:32, empty birthYear/age and consent version 2026-11-simple-v1. Test record intentionally retained; not a real applicant. Email delivery not independently verified.

## Outstanding
Same-page success popup NOT implemented. User's earlier pending work requires current Apps Script source and a verified server response protocol, not just frontend success UI. Current flow navigates to Google-hosted receipt page and works with existing backend. Do not replace the backend using stale packaged code or reorder sheet columns.
