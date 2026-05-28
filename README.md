# ⚡ Synapse Engine Showcase & Regression Metrics

Live performance metrics and automated regression results for the Synapse Core engine. 

**Live Results Dashboard:** [Synapse Engine Showcase](https://synapse-stack.github.io/Synapse-Engine-Showcase/)

## 📌 Repository Scope

This repository serves two primary purposes:

1. **Engine Compatibility Issues:** If a PDF fails, behaves unexpectedly, or triggers an unsupported-format error in the benchmark harness, open an issue here. *(Note: Bug reports for unrelated tooling or infrastructure belong in the core repo).*
2. **Regression Showcase:** Timestamped run logs and corpus metrics that track the engine's evolution over time. Source code for the engine itself lives in `Synapse-Core`.

> **About the Engine:** Synapse is a PDF engine built for high-performance, low-level manipulation. Designed for $O(1)$ performance where data remains strictly in RAM and never touches a disk or third-party server, its architecture supports surgical binary patching. While the engine handles a wide array of features, our current automated regression suite strictly validates the **Watermarking Module** to guarantee core structural integrity before expanding test coverage.


## 🔒 Engine Architecture & Licensing

The source code for `Synapse-Core` is currently maintained in a private repository. 

Synapse is not a standard document wrapper; it is built on proprietary applied mathematics and complex algorithmic models to achieve its `O(1)` processing speeds. Because the engine utilizes novel low-level binary mapping and a strict memory architecture, the core design patterns and mathematical implementations remain closed-source at this time. 

This public showcase repository exists to provide absolute transparency regarding the engine's structural integrity, regression stability, and performance metrics without exposing the underlying proprietary algorithms.
---

## 🎯 The Regression Corpus

To ensure the engine handles extreme edge cases and chaotic file structures without crashing, Synapse runs a 4-tier regression suite against **2,817 PDFs** spanning mobile renderers, vector engines, digital signature suites, office exporters, and industry monoliths.

*A rapid cross-batch **Smoke Test** (5 samples per batch) runs as a pre-flight sanity check to validate basic structure before gating the full pipeline.*

### Batch 1 — Exotic & Fast
Mobile rendering, streaming generators, font layers, and client-side layout engines.

| Corpus | Description | Files |
| :--- | :--- | :--- |
| **Android PDF Viewer** | Mobile rendering surface | 13 |
| **Laravel Snappy** | HTML-to-PDF via headless WebKit | 28 |
| **DejaVu Fonts Suite** | Embedded font stress tests | 39 |
| **OpenPDF** | Cross-platform Java generation | 42 |
| **Apache Nutch** | Text scraper output corpus | 12 |
| **Axway Parsr** | Document structure extraction engine | 15 |
| **Cairo GitLab Vector UI** | Vector-rendered UI documents | 29 |
| **PDFKit** | JS-based streaming generator | 38 |
| **Prawn** | Ruby-based generation engine | 53 |
| **PDFMiner** | Pure Python text extraction layout analyzer | 123 |
| **React-PDF** | Client-side JS rendering and layout wrappers | 14 |
| **Total** | | **406** |

### Batch 2 — Vector & Signed
Vector graphics, binary data transfer, linearisation, and digital signature standards.

| Corpus | Description | Files |
| :--- | :--- | :--- |
| **Cairo Vector Engine** | Full vector pipeline output | 166 |
| **DSS** | Signed document compliance corpus | 243 |
| **qpdf** | Linearisation and structural verification | 111 |
| **pikepdf** | Zero-copy binary data transfer validation | 23 |
| **Total** | | **543** |

### Batch 3 — Medium Heavy
Geometric extraction, heavy office exports, and structural conversion from complex formats.

| Corpus | Description | Files |
| :--- | :--- | :--- |
| **Apache FOP** | Formatting Objects Processor output | 85 |
| **pdfcpu** | Processor suite — repair and normalisation | 94 |
| **LibreOffice Export** | Office-to-PDF export pipeline | 110 |
| **Tabula** | Geometric table extraction (small set) | 2 |
| **Tabula-Java** | Geometric extraction engines (full set) | 77 |
| **Apache POI** | Structural conversions from complex Office XML | 11 |
| **Total** | | **379** |

### Batch 4 — Monoliths
Binary image streams, injected text layers, and industry-standard rendering engines at scale.

| Corpus | Description | Files |
| :--- | :--- | :--- |
| **libvips** | Binary image stream documents | 55 |
| **OCRmyPDF** | Invisible OCR text layer injection | 73 |
| **Evince (GNOME)** | GNOME document suite output | 122 |
| **Master Corpus** | Cross-origin monolith collection | 540 |
| **PDFium** | Google's standard C++ rendering engine | 379 |
| **SumatraPDF** | Native Win32 desktop application output | 320 |
| **Total** | | **1,489** |

### 📊 Corpus Summary

| Batch | Focus | Files |
| :--- | :--- | :--- |
| **1 — Exotic & Fast** | Mobile, streaming, fonts | 406 |
| **2 — Vector & Signed** | Vector graphics, signatures | 543 |
| **3 — Medium Heavy** | Office exports, extraction | 379 |
| **4 — Monoliths** | Image streams, renderers at scale | 1,489 |
| **Total** | | **2,817** |

---

## 📈 Engine Metrics & CI/CD

### Validation Criteria

* **Full-Circuit Integration:** Validates the complete zero-custody pipeline (Scan → Write → Map → Trailer → Merge). The patched buffer must yield a valid `%%EOF` tail and successfully re-scan with a functionally incremented `startxref` pointer.
* **Structural Resiliency:** Ensures the scanner gracefully navigates ISO 32000 edge cases without crashing, explicitly testing mixed line terminators (LF, CRLF, CR), array-based `/Contents`, inherited `/Resources`, and multi-revision files utilizing `/Prev` pointers.
* **5-Stage Smoke Testing:** Probes real-world and malformed files from the veraPDF corpus through a strict 5-stage traversal: `startxref` resolution, `xref` table parsing, `trailer` extraction, `catalog` retrieval, and full `pageTree` walking.
* **$O(1)$ Performance Scaling:** Enforces strict architectural constraints. Surgical patching and incremental append operations on a 100MB payload must execute in under 3x the time of a 1MB payload across 1,000 continuous iterations.

### Success Thresholds
* 🟢 **95%+ (Excellent):** No regressions detected.
* 🟡 **80–95% (Warning):** Minor regressions; acceptable for review.
* 🔴 **< 80% (Critical):** Engine structural issues detected.

---

## 📁 Results Navigation

Detailed, timestamped run logs and metadata are maintained directly in the repository to track the engine's evolution over time.

👉 **[View the Live Benchmark Dashboard](https://synapse-stack.github.io/Synapse-Engine-Showcase/)**
