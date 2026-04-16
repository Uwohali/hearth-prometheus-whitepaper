# Work for Nature, and Nature will work for you

## h•eart•h Prometheus — Sovereign Syntropy
### Verification Guide

This document provides concise instructions for verifying the authenticity and integrity of the official canonical release files.

Verification is based on two independent cryptographic methods:

1. **OpenPGP signature verification** — to authenticate `SHA256_SUMS.txt`
2. **SHA-256 hashing** — to verify that covered files have not been altered

---

## Files involved in the verification chain

- `Uwohali_Tuccio_PUBLIC_KEY.asc`
- `SHA256_SUMS.txt`
- `SHA256_SUMS.txt.asc`

Supporting references:

- `Technical_verification_&_cryptographic_integrity_manual.md`
- `RELEASE_MANIFEST.json`
- `Root_Of_Trust.md`

---

## Step 1 — Import the public key

```bash
gpg --import Uwohali_Tuccio_PUBLIC_KEY.asc
```

Verify the fingerprint:

```bash
gpg --fingerprint Uwohali_Tuccio
```

Expected fingerprint:

```text
D20D FF6C BE33 1B3A 4109 DF84 8C8C B0D4 8C7F 60DA
```

---

## Step 2 — Verify the signed checksum file

```bash
gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt
```

Success criteria:

- the signature is reported as good
- the signer matches Uwohali Tuccio
- the fingerprint matches the root of trust

---

## Step 3 — Verify the covered files

```bash
sha256sum -c SHA256_SUMS.txt
```

All listed files should verify successfully.

---

## Interpretation note

`SHA256_SUMS.txt` should be read together with `RELEASE_MANIFEST.json`.

The checksum file records the authoritative SHA-256 hashes for the canonical text set and selected release metadata included in the current release freeze. Auxiliary materials not included in the checksum set should not be assumed to be covered unless explicitly listed.

---

## Troubleshooting

### Signature fails
- verify that the correct public key was imported
- verify that the checksum file and detached signature belong to the same release
- verify that line endings or file contents have not changed

### Hash check fails
- the file may have been altered
- the file may belong to a different release
- the file may have been resaved with different line endings or encoding

---

## Status note

This file is a normalized draft update prepared for the canonical release freeze. Final verification outputs depend on the final SHA256_SUMS.txt and detached signatures.
