# Release Policy

## Scope

This repository publishes distribution metadata and release assets for Koelman Labs Joomla extensions.

## Rules

1. A Joomla update feed must never advertise a package that does not exist.
2. A published version/tag is immutable. Corrections require a new version.
3. Release packages belong in GitHub Releases, not in the Git tree.
4. Every published package must have a recorded SHA-256 checksum.
5. Compatibility claims must be backed by an explicit test result.
6. Development/source repositories may remain private; public update endpoints must remain accessible without authentication.
7. Pre-release channels must not be presented as stable releases.
8. Rollback/replacement is done by publishing a newer corrected version, not by silently replacing an existing asset.

## uddeIM initial release line

The Joomla 6 Enhanced line starts at:

`6.0.0`

Before the first stable release, use a pre-release such as:

`6.0.0-beta1`

The first advertised package must pass Joomla-native update discovery and upgrade acceptance on the owned disposable Joomla test clone.
