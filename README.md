> 🚧 **Status: active development.** It works for the author; interfaces may change.

# jev-teknik-arastirma

**Jev technical research** — an independent, source-linked write-up (in Turkish, with this English summary) on how Jev's decision-style API could be used as a *decision signal* and where the evidence stops. Source check date: 14 November 2026; links and model versions must be re-checked before relying on them.

## Summary (EN)

- The provider's docs describe four question types (a binary event probability, a choice with a distribution, an ordinal score, and image localisation). The suggested pattern: the application bounds the input, asks the model for a narrow decision signal, and decides the final action with separate rules. This is a design suggestion derived from the docs, not a verified product feature.
- The research separates provider claims, a third-party experiment (`jev-spam-eval`) and local or production evidence. No new API test or production study was run for this write-up; no paid calls were made and no personal data was sent anywhere.
- Limits it points out: numeric reasoning, date comparison, multi-step indirection, irrelevant long context and adversarial content are named by the provider as error-prone, and option order can change an answer. Error rates were not measured independently here.
- A probability-shaped answer is not by itself evidence of calibration. A pilot would need held-out labelled data, per-language and per-critical-class measurement. That is a recommendation, not a result.
- Suggested boundary: start in shadow mode where the result does not change an action; keep critical authority in deterministic checks and human review.
- Unknown / not measured: Turkish-language performance, independent latency, production safety, data retention, SLA and total cost.

This is **not** a product, SDK, security guarantee or production benchmark. It is independent: no affiliation, sponsorship or endorsement relationship with TypeSafe or any other provider.

## Turkey-specific notes

The full research text is in Turkish (`ARASTIRMA.md`). A Turkish summary of this README is below.

**TR** — Jev'in karar arayüzünü ve değerlendirme sınırlarını inceleyen bağımsız araştırma. TypeSafe veya başka bir sağlayıcıyla ortaklık, sponsorluk ya da onay ilişkisi yoktur. Bu çalışma bir ürün, SDK, güvenlik garantisi veya üretim benchmark'ı değildir.

## Files

- [ARASTIRMA.md](ARASTIRMA.md) — the research (Turkish).
- [KAYNAKLAR.md](KAYNAKLAR.md) — sources and verification limits.
- [COPYRIGHT.md](COPYRIGHT.md) — rights and reuse (bilingual).
- [LICENSE](LICENSE) — CC-BY-4.0 legal code.
- [MANIFEST.sha256](MANIFEST.sha256) — SHA-256 of the four Markdown content files; it does not include itself.

## Licence

Text: CC-BY-4.0 (`LICENSE`), Copyright (c) 2026 Kemal (KarıncaAI). Linked third-party material is not covered. Report problems privately, see `SECURITY.md`.
