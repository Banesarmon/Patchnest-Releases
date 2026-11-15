# Patchnest — Official Downloads

This public repository is reserved for **approved Patchnest desktop installers and signed update metadata**.

**Current release status:** No Windows installers have been published here yet. The updater feed has not been activated. Do not download development artifacts from unrelated accounts or websites.

## Installing Patchnest

When a release is approved, the installer will be available in the [Releases section](https://github.com/Banesarmon/Patchnest-Releases/releases), typically named `PatchnestSetup-<version>.exe`.

The desktop app is intended to update itself: **Update app → verify release → download → install → relaunch**. That capability must first pass native Windows update and rollback testing, and it will remain unavailable until the signed feed is configured.

## Security

- Signed update metadata is required before an installer can be selected by Patchnest.
- The installer is checked against the signed release's exact SHA-256 digest and size.
- Never enter GitHub credentials into Patchnest; in-app updates do not need an account.
- No signing *private key*, access token, proprietary source code, or CI secret is stored here.
- Publisher signing of Windows executable files is a separate step from signing update metadata.
- The app never uploads diagnostic details to this repository.

See [Security and verification](SECURITY.md).

## Publishing policy

Nothing is published automatically from the private development repository. Builds are released only after explicit approval, successful automated tests, Windows installation/update/uninstallation testing, and signature verification.

This repository distributes release artifacts, not the application source. All rights remain with the respective owner; public downloads do not imply open-source licensing.
