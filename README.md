# Stream Learning — Presentation Site

A static site that hosts the Stream Learning / ExamRizz pitch deck and its live demos.
Deployed on **Vercel** (linked to this GitHub repo). Every demo the deck links to is a
public, shareable URL — nothing is hosted locally.

## Routes

| URL | Content | Linked from deck |
|-----|---------|------------------|
| `/` | The presentation deck (`index.html`) | — |
| `/demo` | 진단 엔진 데모 — diagnostic walkthrough | 진단평가 · ▶ 데모 보기 |
| `/rubric` | Diagnostic rubric | 진단평가 · 루브릭 보기 |
| `/curriculum` | 조건 기반 영어 작문 커리큘럼 | 작문 · 작문 커리큘럼 |
| `/writing-demo` | Writing demo | 작문 · ▶ 작문 데모 보기 |
| `/question-engine` | 문항 엔진 데모 | 문항 엔진 · ▶ 데모 보기 |
| `/brochure.pdf` | JSB College brochure (camp timetable) | 캠프 · 일정 & 내용 보기 |

## Pending content

`/rubric` and `/writing-demo` currently show branded placeholder pages. Replace
`rubric/index.html` and `writing-demo/index.html` with the real demo files when ready —
the deck already links to these routes, so no deck changes are needed.

## How the deck works

`index.html` is a self-contained bundled export: slide markup and assets live in
`__bundler/template` / `__bundler/manifest` script tags and are unpacked in the browser.
The deck's demo buttons were rewritten from hard-coded Netlify preview URLs to the
relative routes above, so they resolve correctly on whatever domain Vercel serves.

## Deploy

Vercel serves this repo as a static site — no build step. Each folder's `index.html`
resolves at its clean path (`/demo`, `/curriculum`, …) via `vercel.json` (`cleanUrls`).
Push to the connected branch to deploy.
