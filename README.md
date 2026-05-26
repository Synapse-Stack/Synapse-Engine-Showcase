# Synapse Engine - Watermarking Test Results Showcase

![Synapse Logo](https://img.shields.io/badge/Synapse-Watermarking%20Engine-blue)
![Tests](https://img.shields.io/badge/Tests-Automated%20Regression%20Suite-brightgreen)
![PDFs Tested](https://img.shields.io/badge/PDFs%20Tested-1000%2B-orange)

> Real-time performance metrics and test results from the Synapse Core watermarking engine.

## 📊 Latest Status

**Last Updated**: See [LATEST_RUNS.md](./LATEST_RUNS.md)

- ✅ **Watermark Features**: Fully Operational
- 📈 **Test Coverage**: 1,489+ PDFs across 4 batches
- 🚀 **Performance**: Comprehensive regression suite
- 📁 **Results**: Timestamped and organized by run

## 🎯 Test Framework

Synapse Core uses a comprehensive 4-batch regression testing approach:

### Batch 1: Exotic & Fast Layouts
**11 corpus sets** - Tests exotic PDF generation methods and fast rendering engines

| Corpus | Files | Focus |
|--------|-------|-------|
| Android PDF Viewer | 13 | Mobile rendering |
| Laravel Snappy | 28 | wkhtmltopdf wrapper |
| DejaVu Fonts | 39 | Font rendering |
| OpenPDF | 42 | Java PDF generation |
| Apache Nutch | 12 | Web scraping |
| Axway Parsr | 15 | Document parsing |
| Cairo GitLab | 29 | Vector graphics |
| PDFKit | 38 | JavaScript streaming |
| Prawn | 53 | Ruby generation |
| PDFMiner | 123 | Python text extraction |
| React PDF | 14 | Client-side rendering |

**Total**: ~447 PDFs

---

### Batch 2: Vector & Signed Productions
**4 corpus sets** - Tests vector graphics and digitally signed PDFs

| Corpus | Files | Focus |
|--------|-------|-------|
| Cairo | 166 | Vector engine |
| DSS | 243 | Digital signatures |
| qpdf | 111 | PDF linearization |
| pikepdf | 23 | Binary data transfer |

**Total**: ~543 PDFs

---

### Batch 3: Medium Heavyweights
**6 corpus sets** - Tests larger and more complex PDFs

| Corpus | Files | Focus |
|--------|-------|-------|
| FOP | 85 | Apache Formatting Objects |
| pdfcpu | 94 | PDF processing |
| OpenOffice | 110 | Office exports |
| Tabula | 2 | Geometric extraction |
| Tabula Java | 77 | Java extraction |
| POI | 11 | Office XML conversion |

**Total**: ~379 PDFs

---

### Batch 4: Extreme Capacity Monoliths
**6 corpus sets** - Tests massive PDFs and industry-standard engines

| Corpus | Files | Focus |
|--------|-------|-------|
| libvips | 55 | Binary image streams |
| OCRmyPDF | 73 | Text layer injection |
| Evince | 122 | GNOME document suite |
| Master Corpus | 540 | Comprehensive collection |
| PDFium | 379 | Google C++ engine |
| SumatraPDF | 320 | Win32 desktop app |

**Total**: ~1,489 PDFs

---

### Smoke Test: Cross-Batch Sanity Check
**Quick pre-flight validation** - 5 samples from each batch

- ✅ Ensures watermark is applied
- ✅ Validates PDF structure integrity
- ✅ Gates full regression suite runs
- ⏱️ Completes in ~10 minutes

## 📈 Performance Metrics

### Success Rate Thresholds

- 🟢 **95%+**: EXCELLENT - No regressions detected
- 🟡 **80-95%**: WARNING - Minor regressions, acceptable
- 🔴 **<80%**: CRITICAL - Engine issues detected

### What We Test

✅ **Watermark Application**: Verifies watermark is correctly applied
✅ **File Size**: Ensures output is larger than input
✅ **Signature Detection**: Checks for watermark signature (`/SynF1`)
✅ **PDF Integrity**: Validates with qpdf checker
✅ **Timeout Handling**: Ensures processing completes in <60s
✅ **Encrypted PDFs**: Properly skips and reports

### Execution Details

| Aspect | Details |
|--------|----------|
| **Environment** | Ubuntu Latest |
| **Node.js Version** | 22.x |
| **Timeout per PDF** | 60 seconds |
| **Batch Timeout** | 30 minutes |
| **Failure Retention** | 7 days |
| **Frequency** | Every push + weekly scheduled |

## 📁 Results Navigation

### Find Results By Date
