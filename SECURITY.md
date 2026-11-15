# Release security and verification

Patchnest uses two distinct protections:

1. **Release authorization:** a signed `latest.json` manifest, authenticated using an Ed25519 public key bundled in Patchnest.
2. **Installer integrity:** SHA-256 and byte-size verification of the installer against the signed manifest.

HTTPS protects transport. The public release repository does not hold the private signing key.

A signed update manifest has this conceptual shape:

```json
{
  "payload": {
    "product": "Patchnest",
    "platform": "windows-x64",
    "version": "0.65.0",
    "installer_url": "https://github.com/Banesarmon/Patchnest-Releases/releases/download/v0.65.0/PatchnestSetup-0.65.0.exe",
    "size": 12345678,
    "sha256": "<64 hex characters>"
  },
  "signature": "<base64 Ed25519 signature over canonical payload JSON>"
}
```

The values above are illustrative **only**, not a usable update. Never place an unsigned or placeholder `latest.json` at the production update URL.

## Release policy

- The private signing key must be created and protected on the publisher's secure machine.
- Do not include private keys, GitHub tokens, or personal information in a release.
- The corresponding installer binary must be uploaded and verified *before* a new signed manifest is published.
- Installer files should also receive Authenticode code signing before broader consumer distribution.
- No releases have been published by these setup steps.

## Report security issues

Use GitHub's private vulnerability reporting feature if enabled for this repository. Do not post secret keys or sensitive diagnostic data in public issues.
