# Mirror Reproducibility and Verification

## Purpose

The founder mirror verifies and reproduces an upstream canonical release. It does not create a competing release.

## Required upstream evidence

Before mirror admission, `MIRROR_SOURCE.json` must identify:

- canonical repository;
- canonical source commit;
- release repository;
- release tag;
- release manifest SHA-256;
- signer fingerprint;
- provenance or attestation reference;
- verification timestamp;
- verifier identity.

Any required field that remains `null` keeps the mirror in `STAGING_NOT_ACTIVATED`.

## Verification sequence

1. Fetch the canonical source commit.
2. Fetch the named canonical release assets.
3. Verify the release manifest hash.
4. Verify every asset against the manifest.
5. Verify detached signatures against the authorized fingerprint.
6. Verify provenance or build attestation where provided.
7. Compare mirrored artifacts byte-for-byte with the verified release assets.
8. Record exclusions and limitations.
9. Update `STATUS.json`.
10. Refresh staging checksums only after textual freeze and review.

## No divergent signing

The founder mirror must not sign a divergent artifact as if it were the canonical release.

A founder signature may attest that a verified mirror was inspected, but it must not replace the canonical release signature or change upstream bytes.
