\# Work for Nature, and Nature will work for you



\## h•eart•h Prometheus — Sovereign Syntropy

\### Verification Guide



This document provides complete instructions for verifying the authenticity and integrity of all files in the official distribution package of \*\*h•eart•h Prometheus – Sovereign Syntropy\*\*.



Verification is based on two independent cryptographic methods:



1\. \*\*GPG digital signature\*\* – to authenticate the checksum file (`SHA256\_SUMS.txt`) and ensure it comes from the official signer.

2\. \*\*SHA-256 hashes\*\* – to verify that each individual document has not been altered or corrupted.



---



\## Package Contents



| File | Description |

|------|-------------|

| `h•eart•h\_Prometheus\_White\_Paper.md` | White Paper (constitutional framework) |

| `h•eart•h\_intelligence\_Manifesto.md` | Philosophical manifesto |

| `Syntropic\_Sovereignty\_Header.md` | Syntropic Sovereignty Header protocol |

| `CAL-1.0\_Syntropic\_rider\_license.md` | License with syntropic rider |

| `README.md` | Package overview |

| `Technical\_verification\_\&\_cryptographic\_integrity\_manual.md` | Technical manual |

| `Uwohali\_Tuccio\_PUBLIC\_KEY.asc` | Public GPG key of the signer |

| `SHA256\_SUMS.txt` | SHA-256 hashes of all `.md` files |

| `SHA256\_SUMS.txt.asc` | GPG signature of `SHA256\_SUMS.txt` |

| `VERIFICATION.md` | This guide |



---



\## Prerequisites



\### GPG (GNU Privacy Guard)

\- \*\*Linux:\*\* Usually pre‑installed. If not: `sudo apt install gnupg` (Debian/Ubuntu) or equivalent.

\- \*\*macOS:\*\* `brew install gnupg` or download from \[gpgtools.org](https://gpgtools.org).

\- \*\*Windows:\*\* Download and install \[Gpg4win](https://gpg4win.org).



\### SHA-256 hashing tools

\- \*\*Linux/macOS:\*\* `sha256sum` is pre‑installed.

\- \*\*Windows:\*\* PowerShell (`Get-FileHash`) or `certutil` (built‑in).



---



\## Step 1: Import the Public GPG Key



```bash

gpg --import Uwohali\_Tuccio\_PUBLIC\_KEY.asc

Expected output:



text

gpg: key 0xD20DFF6CBE331B3A4109DF848C8CB0D48C7F60DA: public key "Uwohali Tuccio (The Constituent) <uwohali77@gmail.com>" imported

Verify the fingerprint:



bash

gpg --fingerprint Uwohali\_Tuccio

The fingerprint must match:



text

D20D FF6C BE33 1B3A 4109  DF84 8C8C B0D4 8C7F 60DA

Step 2: Verify the Checksums File Signature

bash

gpg --verify SHA256\_SUMS.txt.asc SHA256\_SUMS.txt

Success criteria:

The output must contain a line like:



text

gpg: Good signature from "Uwohali Tuccio (The Constituent) <uwohali77@gmail.com>"

A warning that the key is not certified with a trusted signature is normal if you have not assigned ultimate trust to the key. The critical part is the "Good signature" confirmation.



Step 3: Verify Individual File Hashes

On Linux/macOS:

bash

sha256sum -c SHA256\_SUMS.txt

All files should report as OK.



On Windows (PowerShell):

powershell

Get-Content SHA256\_SUMS.txt | Where-Object { $\_ -match '^\[A-F0-9]{64}' } | ForEach-Object {

&nbsp;   $parts = $\_ -split '\\s+', 2

&nbsp;   $expected = $parts\[0]

&nbsp;   $file = $parts\[1]

&nbsp;   $computed = (Get-FileHash $file -Algorithm SHA256).Hash.ToUpper()

&nbsp;   if ($expected -eq $computed) {

&nbsp;       Write-Host "✅ $file OK" -ForegroundColor Green

&nbsp;   } else {

&nbsp;       Write-Host "❌ $file NOT VALID" -ForegroundColor Red

&nbsp;       Write-Host "   Expected: $expected"

&nbsp;       Write-Host "   Computed: $computed"

&nbsp;   }

}

Step 4: (Optional) Verify Individual Document Signatures

Each .md file has a corresponding detached signature (.asc). You can verify them individually:



bash

gpg --verify Syntropic\_Sovereignty\_Header.md.asc Syntropic\_Sovereignty\_Header.md

gpg --verify h•eart•h\_intelligence\_Manifesto.md.asc h•eart•h\_intelligence\_Manifesto.md

gpg --verify CAL-1.0\_Syntropic\_rider\_license.md.asc CAL-1.0\_Syntropic\_rider\_license.md

gpg --verify h•eart•h\_Prometheus\_White\_Paper.md.asc h•eart•h\_Prometheus\_White\_Paper.md

Troubleshooting

Problem	Solution

"Can't check signature: No public key"	You forgot to import the public key. Go back to Step 1.

"Signature expired"	Check that your system date and time are correct. The signature is valid until March 5, 2028.

Hash mismatch	The file has been altered or corrupted. Download the package again from an official source.

Windows: gpg command not found	Install Gpg4win and ensure it is added to your PATH, or use the full path to gpg.exe.

Security Notes

Always download the public key from a trusted source (official website, key servers, or the included .asc file).



The key fingerprint is the ultimate identifier – verify it through multiple channels if possible.



SHA-256 hashes are collision‑resistant; matching hashes guarantee file integrity.



This verification process establishes a chain of trust: GPG → SHA256\_SUMS.txt → individual files.



References

OpenPGP



SHA-2



Holochain



h•eart•h Prometheus White Paper



For the living earth and generations to come.

Work for Nature, and Nature will work for you.



© 2026 Permaculture DAO LLC

All rights reserved

