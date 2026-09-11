# Release Policy

## Scope

This repository publishes distribution metadata and release assets for Joomla
extensions maintained or distributed by Koelman Labs.

All extensions follow `docs/PUBLIC_RELEASE_STANDARD.md`.

## Rules

1. A Joomla update feed must never advertise a package that does not exist.
2. A published version/tag and its release asset are immutable. Corrections require a new version.
3. Release packages belong in GitHub Releases, not in the Git tree.
4. Every published package must have a recorded SHA-256 checksum and byte size.
5. Compatibility claims must be backed by explicit test evidence.
6. Public update endpoints must remain accessible without authentication.
7. Pre-release channels must not be presented as stable releases.
8. Rollback/replacement is done by publishing a newer corrected version, not by silently replacing an existing asset.
9. The exact artifact that passed acceptance is the artifact that is published.
10. Each extension keeps its own release evidence and compatibility record.

## Release sequence

For a normal public release:

1. prepare version and public metadata;
2. pass source/package validation;
3. build the release artifact;
4. record source revision, SHA-256, and byte size;
5. pass focused install/update acceptance on a disposable environment;
6. publish the exact accepted artifact as a GitHub Release asset;
7. publish/update the Joomla update feed;
8. pass native Joomla discovery/download/install acceptance;
9. record the final release gate;
10. promote to stable only when stable-only gates are green.

## Current uddeIM example

The Joomla 6 Enhanced line starts at `6.0.x`, with first stable target
`6.0.0`. Pre-release candidates such as `6.0.0-beta1` are used to prove the
public distribution pipeline before stable promotion.
