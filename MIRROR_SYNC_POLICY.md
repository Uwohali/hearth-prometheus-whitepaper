# Founder Mirror Synchronization Policy

## Admission rule

An artifact may enter the founder mirror only when:

- its authoritative repository is identified;
- its source commit is immutable and recorded;
- its release tag is recorded;
- manifest and checksums are verified;
- signatures are verified when required;
- provenance is recorded;
- claims remain within the authorized scope;
- exclusions and unresolved findings are disclosed.

## Update rule

Mirror updates use pull requests.

No update may silently replace a canonical artifact, rewrite historical provenance or upgrade a claim.

## Divergence rule

Any byte-level divergence from an admitted canonical artifact must be:

- rejected; or
- clearly classified as founder-authored commentary outside the canonical artifact.

## Withdrawal rule

If upstream evidence is revoked, contradicted or materially corrected, the mirror status must be downgraded and affected claims withdrawn or corrected.
