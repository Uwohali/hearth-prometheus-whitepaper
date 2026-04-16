# Reproducible Release Specification

## h•eart•h Prometheus — Sovereign Syntropy

Constitutional text version: 1.1  
Constitutional text date: March 13, 2026  
Canonical release publication date: April 16, 2026  
Signer: Uwohali Tuccio

---

## Purpose

This document defines the procedure required to reproduce the canonical release of the h•eart•h Prometheus Sovereign Syntropy framework.

The goal is to ensure that an independent auditor, researcher, or contributor can regenerate the release metadata and obtain identical cryptographic hashes for the canonical text set.

---

## Canonical Documents

### Constitutional core

- h•eart•h_Prometheus_White_Paper.md
- h•eart•h_intelligence_Manifesto.md
- Syntropic_Sovereignty_Header.md
- CAL-1.0_Syntropic_rider_license.md

### Supporting legal and trust documents

- CAL-1.0_License.md
- Root_Of_Trust.md
- Uwohali_Tuccio_PUBLIC_KEY.asc

### Verification and reproducibility materials

- VERIFICATION.md
- Technical_verification_&_cryptographic_integrity_manual.md
- REPRODUCIBLE_RELEASE.md
- Runbook.md
- README.md
- RELEASE_MANIFEST.json
- SHA256_SUMS.txt

The authoritative release file set should be interpreted through the current RELEASE_MANIFEST.json.

---

## Deterministic Build Procedure

After the canonical documents have been frozen, normalized, and cross-checked, generate the checksum index for the current canonical text set and release metadata:

```bash
sha256sum *.md RELEASE_MANIFEST.json > SHA256_SUMS.txt
```

Then sign the checksum file:

```bash
gpg --detach-sign --armor SHA256_SUMS.txt
```

---

## Verification Procedure

```bash
gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt
sha256sum -c SHA256_SUMS.txt
```

---

## Root of Trust

Fingerprint:

D20D FF6C BE33 1B3A 4109 DF84 8C8C B0D4 8C7F 60DA

Public key:

Uwohali_Tuccio_PUBLIC_KEY.asc

---

## Status note

This file reflects the normalized release state prepared for the April 16, 2026 canonical publication. Final hashes and signatures must be regenerated after the full document set is frozen.
