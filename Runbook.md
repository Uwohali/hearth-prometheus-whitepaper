# Prometheus Sovereign Syntropy — Canonical Release Runbook

## Purpose

This runbook defines the operational procedure for preparing, freezing, hashing, signing, and verifying a canonical release of the h•eart•h Prometheus Sovereign Syntropy document set.

It is designed to ensure that:

- the constitutional text set is internally coherent
- filenames and references are normalized
- verification materials are aligned with the release
- checksums and signatures are generated only after editorial freeze
- independent auditors can reproduce the release process

---

## Release principle

Do **not** generate hashes or signatures before the canonical document set is frozen.

Any textual change after hashing invalidates:

- per-file `.sha256` files
- `SHA256_SUMS.txt`
- detached `.asc` signatures
- hash references embedded in the White Paper

The release procedure therefore follows this strict order:

1. classify documents
2. freeze content
3. normalize filenames and references
4. align dates and versioning
5. finalize manifest
6. normalize line endings
7. generate checksums
8. generate detached signatures
9. verify release integrity
10. update embedded hash references last

---

## Release classification

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

- README.md
- VERIFICATION.md
- Technical_verification_&_cryptographic_integrity_manual.md
- REPRODUCIBLE_RELEASE.md
- Runbook.md
- RELEASE_MANIFEST.json
- SHA256_SUMS.txt

### Derived / release support materials

- CONTRIBUTING.md
- PROMETHEUS_CANON_12_PAGES.md
- Prometheus_Canon_12_pages.docx
- Prometheus_Canon_12_pages.pdf

---

## Step 1 — Freeze content

Before proceeding, confirm that:

- the White Paper Markdown has been regenerated from the current `.docx` master
- the constitutional seal in the White Paper reflects the 3-document trinity
- all dependent documents have been updated to match the new canonical structure
- no pending editorial changes remain

If any document is still being edited, stop here.

---

## Step 2 — Normalize filenames and references

Ensure that all references use the final filename set.

Critical example:

- use `CAL-1.0_License.md`
- do **not** leave residual references to `the legacy uppercase CAL filename variant`

Search globally for stale references before proceeding.

---

## Step 3 — Align dates and version metadata

Confirm consistency across:

- constitutional text version
- constitutional text date
- canonical release publication date
- signer identity
- publisher identity

Recommended current values:

- Constitutional text version: 1.1
- Constitutional text date: March 13, 2026
- Canonical release publication date: April 16, 2026

If any file still uses old release dates or version numbers inconsistently, correct it now.

---

## Step 4 — Finalize RELEASE_MANIFEST.json

`RELEASE_MANIFEST.json` should become the authoritative inventory of the release.

It should include:

- filename
- role/classification
- checksum coverage status
- signature status
- release date
- optional notes

No hashes should be inserted until the file list is final.

---

## Step 5 — Normalize line endings

Before hashing, normalize line endings for all text files.

Recommended policy:

- Markdown / text / JSON / shell files → LF

Do not mix CRLF and LF in the canonical release set.

If a file is re-saved with different line endings after hashing, verification will fail.

---

## Step 6 — Generate per-file checksums

After freeze, generate per-file `.sha256` files for release-critical documents.

Examples:

```bash
sha256sum "h•eart•h_Prometheus_White_Paper.md" > "h•eart•h_Prometheus_White_Paper.md.sha256"
sha256sum "Syntropic_Sovereignty_Header.md" > "Syntropic_Sovereignty_Header.md.sha256"
sha256sum "h•eart•h_intelligence_Manifesto.md" > "h•eart•h_intelligence_Manifesto.md.sha256"
sha256sum "CAL-1.0_Syntropic_rider_license.md" > "CAL-1.0_Syntropic_rider_license.md.sha256"
sha256sum "Technical_verification_&_cryptographic_integrity_manual.md" > "Technical_verification_&_cryptographic_integrity_manual.md.sha256"
```

Add others as required by the release policy.

---

## Step 7 — Generate SHA256_SUMS.txt

After per-file checksums are decided, generate the checksum index for the canonical text set and release metadata.

Example baseline procedure:

```bash
sha256sum *.md RELEASE_MANIFEST.json > SHA256_SUMS.txt
```

Only use this command if the file set and naming are already frozen.

---

## Step 8 — Generate detached signatures

After the checksum file is final, generate detached OpenPGP signatures.

Minimum required:

```bash
gpg --detach-sign --armor SHA256_SUMS.txt
```

Optional per-file signatures may also be generated for selected canonical documents:

```bash
gpg --detach-sign --armor "h•eart•h_Prometheus_White_Paper.md"
gpg --detach-sign --armor "Syntropic_Sovereignty_Header.md"
gpg --detach-sign --armor "h•eart•h_intelligence_Manifesto.md"
gpg --detach-sign --armor "CAL-1.0_Syntropic_rider_license.md"
```

---

## Step 9 — Verify the release

Run both signature and checksum verification.

```bash
gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt
sha256sum -c SHA256_SUMS.txt
```

Expected result:

- valid signature
- all covered files verify successfully

---

## Step 10 — Update embedded hash references last

Only after successful verification should you update embedded SHA-256 references inside:

- h•eart•h_Prometheus_White_Paper.md
- documentation that cites exact hashes
- release notes if applicable

This is the final editorial step.

If hashes are inserted before the verification set is final, the White Paper will immediately become outdated again.

---

## Legacy tooling note

Do not use any legacy release script that regenerates outdated document contents or stale canonical sets.

If a legacy script still references:

- `the legacy uppercase CAL filename variant`
- old version numbers
- old release dates
- obsolete package contents

it must be archived or replaced before the release process continues.

---

## Completion criteria

A canonical release is complete only when all of the following are true:

- document set is frozen
- filenames are normalized
- references are aligned
- RELEASE_MANIFEST.json is finalized
- line endings are normalized
- SHA256_SUMS.txt is regenerated
- detached signatures are regenerated
- verification passes cleanly
- embedded hash references have been updated last

Only then is the release fit to be published as canonical.
