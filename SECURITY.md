# Security Policy

## Private vulnerability reporting

Use GitHub's private vulnerability reporting interface for this repository:

1. Open the repository **Security** tab.
2. Select **Report a vulnerability**.
3. Submit the report privately.

Do not disclose credentials, private keys, tokens, personal data, unreleased evidence or exploitable details in a public issue.

## Scope

This repository is a founder publication mirror.

Runtime and application vulnerabilities belong in the relevant implementation repositories:

- `Permaculture-DAO/prometheus-happ`
- `Permaculture-DAO/prometheus-runtime`

Release-integrity, provenance, checksum, signature and mirror-admission defects are in scope here.

## Release-integrity incident procedure

A suspected manifest, checksum, signature, provenance or byte-parity failure triggers:

1. publication freeze;
2. mirror status downgrade;
3. affected-claim review;
4. correction or withdrawal;
5. documented independent re-verification.

## Response boundary

A private report does not establish that a vulnerability, integrity defect or claim failure exists. Findings remain provisional until triaged, reproduced and assigned a documented disposition.
