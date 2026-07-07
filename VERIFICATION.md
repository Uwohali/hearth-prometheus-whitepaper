# Founder Mirror Verification

## Scope

Mirror verification covers:

- upstream repository identity;
- source commit SHA;
- canonical release tag;
- release manifest integrity;
- asset SHA-256 integrity;
- detached-signature verification;
- signer fingerprint;
- provenance or attestation evidence;
- byte-for-byte comparison;
- UTF-8 and line-ending normalization for mirror-authored governance files;
- claims-boundary conformance;
- status and exclusion accuracy.

## Staging rule

While `MIRROR_SOURCE.json` contains unresolved required fields, the mirror remains:

`STAGING_NOT_ACTIVATED`

Staging checksums are integrity aids only. They are not canonical signatures and do not establish scientific, legal, production or financial admission.

## Self-hash rule

A document must not contain its own final hash inside the hashed body.

Hashes belong in external manifests and checksum files.
