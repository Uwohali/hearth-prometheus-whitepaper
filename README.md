# h•eart•h Prometheus — Sovereign Syntropy

Canonical cryptographic release of the h•eart•h Prometheus White Paper, its constitutionally incorporated documents, and its verification and reproducibility set.

This package contains the official canonical release artifacts for the h•eart•h Prometheus Sovereign Syntropy framework.

All release-critical files are designed to be independently verifiable through SHA-256 hashes and OpenPGP signatures.

---

## Release identity

- Constitutional text version: 1.1+
- Constitutional text date: March 13, 2026
- Canonical release publication date: April 16, 2026
- Previous canonical freeze superseded: April 9, 2026
- Canonical signer: Uwohali Tuccio
- Canonical publisher: Permaculture DAO LLC

---

## Ontological note

The current constitutional language should be read with the following semantic hierarchy:

- **Prometheus** = capital-ready regenerative transformation infrastructure
- **PRU** = translation / underwriting / financial abstraction layer
- **TRBK** = governance / coordination / participation layer
- **HoloFuel** = operational transaction / infrastructure layer
- **OHE** = minimum deployable regenerative unit
- **autopoietic layer** = adaptive intelligence and risk-compression layer

This hierarchy governs the canonical reading of the white paper and should remain consistent across derived constitutional materials, repository READMEs, and pilot-facing documentation.

---

## Package contents

### Constitutional core

- `h•eart•h_Prometheus_White_Paper.md`
- `h•eart•h_intelligence_Manifesto.md`
- `Syntropic_Sovereignty_Header.md`
- `CAL-1.0_Syntropic_rider_license.md`

### Supporting legal and trust documents

- `CAL-1.0_License.md`
- `Root_Of_Trust.md`
- `Uwohali_Tuccio_PUBLIC_KEY.asc`

### Verification and reproducibility set

- `Technical_verification_&_cryptographic_integrity_manual.md`
- `VERIFICATION.md`
- `REPRODUCIBLE_RELEASE.md`
- `Runbook.md`
- `RELEASE_MANIFEST.json`
- `SHA256_SUMS.txt`
- `SHA256_SUMS.txt.asc`

### Release support and derived materials

- `README.md`
- `CONTRIBUTING.md`
- `PROMETHEUS_CANON_12_PAGES.md`
- `Prometheus — Executive Summary & Investment Thesis.md`
- `Prometheus_Canon_12_pages.docx`
- `Prometheus_Canon_12_pages.pdf`

---

## Repository alignment

Canonical project development lives under the `Permaculture-DAO` organization.

Repository-bounded implementation, operations, evaluation logic, bridge services, UI, and pilot runtime materials are maintained separately through the organizational repository architecture and must not silently redefine canonical semantics.

The constitutional rule is simple:

- the Canon defines enduring architectural meaning at high level
- repository README files define repository-specific scope
- implementation behavior remains bounded by pilot-first discipline
- runtime code does not silently redefine constitutional intent

---

## Verification quick start

1. Import the public key:
   `gpg --import Uwohali_Tuccio_PUBLIC_KEY.asc`

2. Verify the signed checksum file:
   `gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt`

3. Verify file integrity:
   `sha256sum -c SHA256_SUMS.txt`

For complete verification instructions, see:

- `VERIFICATION.md`
- `Technical_verification_&_cryptographic_integrity_manual.md`

---

## Status note

This README reflects the ontology-synchronized canonical release state prepared for publication on April 16, 2026. Hashes, signatures, manifest references, and any binary derived artifacts must be regenerated after the full document set is finalized.
