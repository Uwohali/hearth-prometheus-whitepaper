Work for Nature,
and Nature will work for you

# h•eart•h Prometheus — Sovereign Syntropy
## The syntropic kernel for autonomous life-systems
### A human pact for h•eart•h intelligence

**Readme & Constitution package**
Version: 1.0
Date: February 26, 2026
Status: Final release

---

## Documents included

### Core documents (with detached GPG signatures)

- **White Paper** (Articles I-XV + Appendices): `h•eart•h_Prometheus_White_Paper.md`
  Signature: `h•eart•h_Prometheus_White_Paper.md.asc`

- **Syntropic Sovereignty Header**: `Syntropic_Sovereignty_Header.md`
  Signature: `Syntropic_Sovereignty_Header.md.asc`

- **h•eart•h intelligence Manifesto**: `h•eart•h_intelligence_Manifesto.md`
  Signature: `h•eart•h_intelligence_Manifesto.md.asc`

- **CAL-1.0 Syntropic rider license**: `CAL-1.0_Syntropic_rider_license.md`
  Signature: `CAL-1.0_Syntropic_rider_license.md.asc`

### Verification Files

- `SHA256_SUMS.txt` – All document hashes
- `SHA256_SUMS.txt.asc` – GPG signature of the checksums file
- `Uwohali_Tuccio_PUBLIC_KEY.asc` – Public key for verification
- `VERIFICATION.md` – Complete verification guide (cross-platform)

---

## How to verify authenticity

### Step 1: Import the public key

`gpg --import Uwohali_Tuccio_PUBLIC_KEY.asc`

Expected output:
`gpg: key 0xD20DFF6CBE331B3A4109DF848C8CB0D48C7F60DA: public key "Uwohali Tuccio (The Constituent) <uwohali77@gmail.com>" imported`

### Step 2: Verify the checksums file signature

`gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt`

### Step 3: Verify individual file hashes

**On Linux/macOS:**
`sha256sum -c SHA256_SUMS.txt`

**On Windows (PowerShell):**
`Get-Content SHA256_SUMS.txt | Where-Object { $_ -match '^[A-F0-9]{64}' } | ForEach-Object { $parts = $_ -split '\s+', 2; $expected = $parts[0]; $file = $parts[1]; $computed = (Get-FileHash $file -Algorithm SHA256).Hash.ToUpper(); if ($expected -eq $computed) { Write-Host "$file OK" -ForegroundColor Green } else { Write-Host "$file NOT VALID" -ForegroundColor Red } }`

### Step 4: (Optional) Verify individual document signatures

`gpg --verify Syntropic_Sovereignty_Header.md.asc Syntropic_Sovereignty_Header.md`

`gpg --verify h•eart•h_intelligence_Manifesto.md.asc h•eart•h_intelligence_Manifesto.md`

`gpg --verify CAL-1.0_Syntropic_rider_license.md.asc CAL-1.0_Syntropic_rider_license.md`

`gpg --verify h•eart•h_Prometheus_White_Paper.md.asc h•eart•h_Prometheus_White_Paper.md`

---

## Important security note

- Previous key `0x307C0CA12424930B` was revoked on 2026-02-10.
- All documents have been re-signed with the current active key (see fingerprint above).
- SHA-256 content hashes remain the authoritative identifier for each document version.

---

## Framework custodian

Uwohali Tuccio  
Permaculture DAO LLC

> "Work for Nature, and Nature will work for you."

---

## Cryptographic integrity

This package establishes a verifiable chain of trust:

1. GPG signatures on all core documents (current active key)
2. SHA-256 hashes cryptographically incorporated into the White Paper (Section 3)
3. Signed checksums file (`SHA256_SUMS.txt.asc`) for complete verification
4. Public key included for independent validation

All documents are constitutionally bound by the eternity clauses (Articles I, II, III, IV, X, XIII) and the Access Covenant (Article XV, Section 5), which cannot be amended or violated.

---

## Package details

- **Format**: UNIX LF (Line Feed)
- **Encoding**: UTF-8 without BOM
- **Generated**: February 26, 2026
- **Canonical Package**: `h•eart•h_Prometheus_Sovereign_Syntropy_2026-02-25.zip`
- **Developers Package**: `h•eart•h_Prometheus_Developers_2026-02-25.zip`

---

*This readme is part of the constitutionally incorporated documents. Its validity derives from the cryptographic integrity of the package it describes.*

© 2026 Permaculture DAO LLC
All rights reserved
