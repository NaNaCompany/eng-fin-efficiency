# 방열핀 효율 계산기

일정한 단면을 가진 곧은 핀의 실제 열방출량을 핀 전체가 기저 온도일 때의 이상적인 열방출량과 비교합니다.

- ID: E152
- App: https://nanalab.kr/eng-fin-efficiency/
- Repository: https://github.com/NaNaCompany/eng-fin-efficiency
- Formula: m = √(hP/(kA꜀)); η = tanh(mL)/(mL); mL → 0: η → 1

## Model and data

정상 1차원 전도, 일정한 단면·열전도율·대류계수·주위 온도, 균일한 기저 온도, 끝단 단열을 가정합니다. 횡단면 온도차·복사·접촉 열저항은 제외합니다. P는 측면 대류 면적을 만드는 둘레이며 끝단 면적은 포함하지 않습니다. h=0 또는 L=0이면 효율의 극한값 1을 표시하며 열방출량이 있다는 뜻은 아닙니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
