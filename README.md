# h•eart•h Prometheus — Sovereign Syntropy

Canonical cryptographic release of the h•eart•h Prometheus White Paper and its constitutionally incorporated documents.

This repository contains the official release artifacts for the h•eart•h Prometheus Sovereign Syntropy framework. All files are cryptographically signed and verifiable.

## 📦 Contents

| File | Description |
|------|-------------|
| `h•eart•h_Prometheus_White_Paper.md` | The White Paper (constitutional framework) |
| `h•eart•h_intelligence_Manifesto.md` | Philosophical manifesto |
| `Syntropic_Sovereignty_Header.md` | Syntropic Sovereignty Header protocol |
| `CAL-1.0_Syntropic_rider_license.md` | License with syntropic governance rider |
| `Technical_verification_\&_cryptographic_integrity_manual.md` | Complete verification manual |
| `VERIFICATION.md` | Quick verification guide |
| `README.md` | This file |
| `SHA256_SUMS.txt` | SHA‑256 hashes of all `.md` files |
| `SHA256_SUMS.txt.asc` | GPG signature of the checksum file |
| `RELEASE_MANIFEST.json` | Full manifest of all files and their hashes |
| `RELEASE_MANIFEST.json.asc` | GPG signature of the manifest |
| `Uwohali_Tuccio_PUBLIC_KEY.asc` | Public GPG key of the signer |
| `h•eart•h_Prometheus_Sovereign_Syntropy_2026-03-05.zip` | Complete ZIP archive (Sovereign Syntropy package) |
| `h•eart•h_Prometheus_Developers_2026-03-05.zip` | Identical ZIP archive (Developers package) |

## 👩‍💻 For developers

The h•eart•h Prometheus Holochain hApp is the reference implementation of the kernel syntropic intelligence.  
If you are a developer, you can find the repository here:

🔗 [github.com/Uwohali/hearth-prometheus-happ](https://github.com/Uwohali/hearth-prometheus-happ)

### Contribution guidelines

Before contributing, please read our Contributor Guidelines, which include the Access Covenant, the Eternity Clauses, and technical instructions for signing commits:

📄 [CONTRIBUTING.md](https://github.com/Uwohali/hearth-prometheus-happ/blob/main/CONTRIBUTING.md)

The file is cryptographically signed and its integrity can be verified with the provided `.asc` and `.sha256` files in the same repository.

All commits in the hApp repository must be signed with GPG to ensure authenticity and traceability. Instructions are provided in the `CONTRIBUTING.md`.

## 🔍 How to verify authenticity

### Prerequisites

- GPG (GNU Privacy Guard) – [Download Gpg4win](https://gpg4win.org) for Windows, or use `brew install gnupg` on macOS / `sudo apt install gnupg` on Linux.
- SHA‑256 hashing tool – `sha256sum` on Linux/macOS, `Get-FileHash` on PowerShell, or `certutil` on Windows.

### Step 1: Import the public key

```bash
gpg --import Uwohali_Tuccio_PUBLIC_KEY.asc
Expected output:

text
gpg: key 0xD20DFF6CBE331B3A4109DF848C8CB0D48C7F60DA: public key "Uwohali Tuccio (The Constituent) <uwohali77@gmail.com>" imported
Key fingerprint:
D20D FF6C BE33 1B3A 4109 DF84 8C8C B0D4 8C7F 60DA
Step 2: Verify the Checksum File Signature
bash
gpg --verify SHA256_SUMS.txt.asc SHA256_SUMS.txt
Look for Good signature in the output.

Step 3: Verify Individual File Hashes
On Linux/macOS:

bash
sha256sum -c SHA256_SUMS.txt
On Windows (PowerShell):

powershell
Get-Content SHA256_SUMS.txt | Where-Object { $_ -match '^[A-F0-9]{64}' } | ForEach-Object {
    $parts = $_ -split '\s+', 2
    $expected = $parts[0]
    $file = $parts[1]
    $computed = (Get-FileHash $file -Algorithm SHA256).Hash.ToUpper()
    if ($expected -eq $computed) {
        Write-Host "✅ $file OK" -ForegroundColor Green
    } else {
        Write-Host "❌ $file NOT VALID" -ForegroundColor Red
    }
}
All files should report OK.

Step 4: (Optional) Verify Individual Document Signatures
Each .md file has a corresponding detached signature (.asc). Verify them individually:

bash
gpg --verify Syntropic_Sovereignty_Header.md.asc Syntropic_Sovereignty_Header.md
gpg --verify h•eart•h_intelligence_Manifesto.md.asc h•eart•h_intelligence_Manifesto.md
gpg --verify CAL-1.0_Syntropic_rider_license.md.asc CAL-1.0_Syntropic_rider_license.md
gpg --verify h•eart•h_Prometheus_White_Paper.md.asc h•eart•h_Prometheus_White_Paper.md
🧾 Encoding Note
All text files (.md, .asc, .json, .txt) are saved in UTF‑8 without BOM.
To view them correctly, use an editor that fully supports UTF‑8 (e.g., Visual Studio Code, Sublime Text, Notepad++).
Windows Notepad may not display special characters (such as • or Greek letters) properly.

🔐 Cryptographic integrity
This package establishes a verifiable chain of trust:

GPG signatures on all core documents (current active key).

SHA‑256 hashes cryptographically incorporated into the White Paper.

Signed checksums file (SHA256_SUMS.txt.asc).

Public key included for independent validation.

All documents are constitutionally bound by the eternity clauses (Articles I, II, III, IV, X, XIII) and the Access Covenant (Article XV, Section 5), which cannot be amended or violated.

📅 Release details
Date: March 5, 2026

Version: v1.0.2

Signer: Uwohali Tuccio

Key ID: 0xD20DFF6CBE331B3A4109DF848C8CB0D48C7F60DA

🧪 For developers (Legacy Note)
The developer ZIP archive is identical and contains all the files listed above. It's provided to make it easy to integrate these documents into your projects or hApps.

For the active development repository, please refer to the h•eart•h Prometheus Holochain hApp.

📚 References
OpenPGP

SHA‑2

Holochain

h•eart•h Prometheus White Paper

Work for Nature, and Nature will work for you.

© 2026 Permaculture DAO LLC
All rights reserved
