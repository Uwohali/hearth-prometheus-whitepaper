# h•eart•h Prometheus — Sovereign Syntropy  
## Release & Verification RUNBOOK

> Goal: ensure that every release of **h•eart•h Prometheus — Sovereign Syntropy** is
> verifiable, reproducible, and cryptographically consistent across Windows, WSL, and Linux/macOS environments.

---

## 0. Operational Glossary

- **Canonical documents**: the 7 constitutional documents versioned and hashed in `SHA256_SUMS.txt`.
- **Public package**: folder `PUBLIC_RELEASE_YYYY-MM-DD` containing:
  - the canonical documents,
  - `SHA256_SUMS.txt` + `.asc`,
  - `RELEASE_MANIFEST.json` + `.asc`,
  - user ZIPs (`h•eart•h_Prometheus_Sovereign_Syntropy_YYYY-MM-DD.zip`, `..._Developers_...`).
- **Sovereign key**:  
  - Fingerprint: `D20D FF6C BE33 1B3A 4109  DF84 8C8C B0D4 8C7F 60DA`  
  - UID: `Uwohali Tuccio <uwohali77@gmail.com>`

---

## 1. Repository Structure

Recommended structure on Windows (F: drive):

```text
F:\hearth intelligence – Prometheus Sovereign Syntropy\
  documenti\
    White Paper\
      Prometheus-canonici\
        CAL-1.0_Syntropic_rider_license.md
        Syntropic_Sovereignty_Header.md
        h•eart•h_intelligence_Manifesto.md
        h•eart•h_Prometheus_White_Paper.md
        README.md
        VERIFICATION.md
        Technical_verification_&_cryptographic_integrity_manual.md
        SHA256_SUMS.txt
        SHA256_SUMS.txt.asc
        Uwohali_Tuccio_PUBLIC_KEY.asc
        PUBLIC_RELEASE_2026-02-18\
          [release materials + ZIPs]
        RUNBOOK.md     ← (this file)