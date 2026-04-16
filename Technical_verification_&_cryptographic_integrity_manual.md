# Work for Nature, and Nature will work for you

## h•eart•h Prometheus — Sovereign Syntropy
### Technical verification & cryptographic integrity manual

**Author:** Uwohali Tuccio  
**Publisher:** Permaculture DAO LLC  
**Constitutional text version:** 1.1  
**Constitutional text date:** March 13, 2026  
**Canonical release publication date:** April 16, 2026  
**Status:** Canonical release update pending checksum and signature regeneration  

---

## 1. Introduction

This manual explains how to verify the cryptographic integrity and authenticity of the canonical release of the **h•eart•h Prometheus Sovereign Syntropy** framework.

The verification architecture is based on:

- SHA-256 hashing
- OpenPGP signatures
- deterministic release procedures
- manifest-based release classification

This guarantees:

- integrity
- authenticity
- independent auditability
- release reproducibility
- source-of-truth discipline

---

## 2. Canonical document set

The Prometheus release is structured in three distinct layers.

### Constitutional core

- h•eart•h_Prometheus_White_Paper.md
- h•eart•h_intelligence_Manifesto.md
- Syntropic_Sovereignty_Header.md
- CAL-1.0_Syntropic_rider_license.md

### Supporting legal and trust documents

- CAL-1.0_License.md
- Root_Of_Trust.md
- Uwohali_Tuccio_PUBLIC_KEY.asc

### Verification, reproducibility, and release integrity materials

- VERIFICATION.md
- Technical_verification_&_cryptographic_integrity_manual.md
- REPRODUCIBLE_RELEASE.md
- README.md
- Runbook.md
- RELEASE_MANIFEST.json
- SHA256_SUMS.txt

The current release manifest defines the authoritative file set for the canonical release.

Where SHA256_SUMS.txt is used as the checksum index, it should be understood as covering the canonical text set and selected release metadata defined for the current release, rather than every possible auxiliary artifact by default.

---

## 3. Cryptographic architecture

The verification chain is structured as follows:

Public key  
↓  
SHA256_SUMS.txt.asc  
↓  
SHA256_SUMS.txt  
↓  
Canonical release files

The file **SHA256_SUMS.txt** contains the authoritative SHA-256 hashes of the canonical text set and selected release metadata.

The file **SHA256_SUMS.txt.asc** contains the OpenPGP signature of the checksum file.

Any modification to a file covered by the checksum set changes its SHA-256 hash and invalidates the signature chain.

---

## 4. Root of trust

The release is anchored to the OpenPGP key of the constitutional steward.

**Fingerprint:**  
D20D FF6C BE33 1B3A 4109 DF84 8C8C B0D4 8C7F 60DA

**Public key file:**  
Uwohali_Tuccio_PUBLIC_KEY.asc

---

## 5. Verification procedure

### Step 1 — Import the public key

```bash
gpg --import Uwohali_Tuccio_PUBLIC_KEY.asc
```

### Step 2 — Verify the checksum signature

```bash
gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt
```

Expected result:

- Good signature from "Uwohali Tuccio"
- fingerprint matches the root of trust above

### Step 3 — Verify file integrity

```bash
sha256sum -c SHA256_SUMS.txt
```

All covered files should verify successfully.

---

## 6. Release discipline

A canonical release should only be hashed and signed after:

1. document classification is frozen
2. filenames are normalized
3. dates and versions are aligned
4. cross-references are updated
5. RELEASE_MANIFEST.json is finalized
6. line endings are normalized

Only after that point should SHA256_SUMS.txt and detached signatures be regenerated.

---

## 7. Constitutional note

The White Paper incorporates three constitutional documents as its legal-technical trinity:

- Syntropic_Sovereignty_Header.md
- h•eart•h_intelligence_Manifesto.md
- CAL-1.0_Syntropic_rider_license.md

Verification and reproducibility materials support the release, but they do not expand the incorporated constitutional trinity.

---

## 8. Status note

This file is a normalized draft update prepared for the canonical release freeze. Final hashes, signatures, and manifest alignment must be regenerated after the full document set is frozen.
