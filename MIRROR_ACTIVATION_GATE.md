# Founder Mirror Activation Gate

## Current decision

This repository is intentionally restricted to:

`STAGING_NOT_ACTIVATED`

The current workflow does not claim to perform canonical-release admission.

## Why the gate is fail closed

Local booleans, locally generated hashes and a locally authored manifest are not independent proof of:

- an authoritative source commit;
- a published canonical release;
- a valid detached signature;
- an authorized signer;
- provenance or build attestation;
- byte parity with authoritative release assets.

Therefore changes to `canonical/` and creation of `CANONICAL_ADMISSION.json` are prohibited by the current workflow.

## Required future activation pull request

A future non-staging transition must introduce a separately reviewed verifier that:

1. fetches the immutable source commit from `Permaculture-DAO/prometheus-canon`;
2. fetches the named release and release manifest from `Permaculture-DAO/prometheus-canonical-releases`;
3. recomputes the release-manifest digest;
4. verifies every release asset against that manifest;
5. verifies detached signatures against a pinned and independently established trust root;
6. verifies the named provenance or attestation;
7. rejects symlinks and unexpected Git object modes;
8. compares every mirrored artifact byte-for-byte with the verified release asset;
9. records exclusions, limitations, verifier identity and review time;
10. requires accountable human approval before merge.

Until that verifier and evidence exist, the mirror must remain staging-only.
