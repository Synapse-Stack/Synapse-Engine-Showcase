# ⚡ Synapse Engine Showcase

![Synapse Core](https://img.shields.io/badge/Synapse-Core%20Engine-blue)
![Tests](https://img.shields.io/badge/Automated%20Regression-Live-brightgreen)
![PDFs Tested](https://img.shields.io/badge/Corpus-1400%2B%20Files-orange)

> Live performance metrics and automated regression results for the Synapse Core engine.

Synapse is built for high-performance, low-level PDF manipulation. While the engine's architecture is designed to support a wide array of surgical document processing features, our current automated regression suite strictly validates the **Watermarking Module** to guarantee core structural integrity before expanding test coverage.

---

## 🎯 The Regression Corpus

To ensure the engine handles extreme edge cases and chaotic file structures without crashing, Synapse runs a 4-tier regression suite. We test against fast client-side rendering engines, strict digital signature standards, and massive industry monoliths.

| Batch | Validation Focus | Key Corpora Samples | Total PDFs |
| :--- | :--- | :--- | :--- |
| **1. Exotic & Fast** | Mobile rendering, streaming, font layers | PDFKit, Prawn, OpenPDF, Android | ~447 |
| **2. Vector & Signed** | Vector graphics, binary transfer, signatures | Cairo, DSS, qpdf, pikepdf | ~543 |
| **3. Medium Heavy** | Geometric extraction, heavy office exports | OpenOffice, pdfcpu, Tabula | ~379 |
| **4. Monoliths** | Binary image streams, injected text layers | PDFium, SumatraPDF, Evince | ~1,489 |

*Note: A rapid cross-batch **Smoke Test** (5 samples per batch) runs as a pre-flight sanity check to validate basic structure before gating the full 30-minute pipeline.*

---

## 📈 Engine Metrics & CI/CD

### Validation Criteria
* **Engine Operations:** Successful watermark application and `/SynF1` signature verification.
* **Document Integrity:** Output validated via strict `qpdf` structural checks.
* **Performance:** Rigid 60-second processing timeout per document.

### Success Thresholds
* 🟢 **95%+ (Excellent):** No regressions detected.
* 🟡 **80-95% (Warning):** Minor regressions; acceptable for review.
* 🔴 **<80% (Critical):** Engine structural issues detected.

---

## 📁 Results Navigation

Detailed, timestamped run logs and metadata are maintained directly in the repository to track the engine's evolution over time.

**Last Updated**: [https://synapse-stack.github.io/Synapse-Engine-Showcase/]
