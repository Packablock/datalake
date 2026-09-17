# 🌐 Packablock Open Datalake

> High-integrity public intelligence datasets for software supply chain security, regulatory compliance, and cybersecurity risk benchmarks.

---

## 🏛️ Open Data Philosophy
This datalake adheres to an **"Open Data, Paid Ergonomics"** model:
- All raw datasets are **100% public, free, and auditable**.
- Served via global edge CDN at [`https://data.packablock.com/`](https://data.packablock.com/) and GitHub raw edge.
- Automated updates are scheduled and cryptographically committed by Packablock ingestion engines.

---

## 📂 Datalake Layout

```
├── supply-chain/
│   ├── runtime-sbom-matrix.csv     # Cloud tools (K8s, Terraform) mapped to engines and PURLs
│   ├── parser-quirks.json          # Syntax traps and unquoted boolean quirks (YAML 1.1 vs 1.2)
│   └── deps-ossf.json              # OpenSSF Scorecards, licenses, and dependency lag benchmarks
├── regulatory/
│   ├── cra-penalties.json          # EU Cyber Resilience Act statutory penalty baselines
│   └── sec-8k-incidents.json       # SEC Form 8-K Item 1.05 cybersecurity material incident filings
├── benchmarks/
│   ├── cisa-kev-epss.csv           # CISA Known Exploited Vulnerabilities joined with EPSS scores
│   └── breach-settlements.csv      # FTC, HHS OCR, and state AG breach settlements & fines
└── telecom/
    ├── isp-labels.csv              # FCC Broadband Consumer Nutrition Label metrics
    └── iot-trust-mark.json         # Smart home & IoT Cyber Trust Mark compliance baselines
```

---

## ⚡ Global Edge Access
Any dataset can be fetched without authentication via HTTPS:

```bash
# Fetch latest runtime SBOM crosswalk
curl -s https://data.packablock.com/supply-chain/runtime-sbom-matrix.csv

# Fetch live CISA KEV + EPSS risk crosswalk
curl -s https://data.packablock.com/benchmarks/cisa-kev-epss.csv
```

### Google Sheets Integration
All CSV files are optimized for native zero-auth formula ingestion:
```excel
=IMPORTDATA("https://data.packablock.com/supply-chain/runtime-sbom-matrix.csv")
```

---

## 📄 License
All datasets in this repository are published under the **Creative Commons Attribution 4.0 International (CC-BY-4.0)** and **MIT** licenses.
