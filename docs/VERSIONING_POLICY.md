# Versioning Policy

Koelman Labs Joomla extensions use explicit extension versions independent of
the Joomla CMS version.

## General rules

- The extension version identifies the extension release.
- Joomla compatibility is declared separately.
- A version must not be reused for different package bytes.
- A correction to a published artifact requires a new version.
- Pre-release identifiers such as `alpha`, `beta`, and `rc` are allowed.
- Stable and pre-release channels must be clearly distinguishable.

Recommended progression where appropriate:

`X.Y.Z-alpha1 -> X.Y.Z-beta1 -> X.Y.Z-rc1 -> X.Y.Z`

The major version does not automatically mean compatibility with the same Joomla
major version. Compatibility remains independently test-backed.

## uddeIM Joomla 6 Enhanced example

- historical upstream base used for migration testing: `5.6.3`;
- Joomla 6 Enhanced release line: `6.0.x`;
- first stable target: `6.0.0`.
