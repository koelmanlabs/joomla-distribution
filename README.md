# Koelman Labs — Joomla Distribution

Public distribution repository for Joomla extensions maintained or distributed
by **Koelman Labs**.

This repository is the public delivery layer for Joomla release packages,
update feeds, compatibility metadata, checksums, and release policy.

It is intentionally separate from development repositories.

## What this repository is for

This repository provides the public files Joomla needs to discover and install
extension updates safely.

It contains:

- Joomla native update XML feeds;
- GitHub Release metadata and release assets;
- compatibility policy;
- versioning policy;
- public release requirements;
- release checklists;
- integrity information such as SHA-256 checksums;
- provenance and maintenance notes where relevant.

Development source code may live in a different repository and may be public or
private depending on the project.

## How releases are distributed

Installable ZIP packages are published as **GitHub Release assets**.

They are not committed directly into the Git tree.

A Joomla update feed is published only after the exact release asset exists and
its identity has been verified.

Typical delivery flow:

```text
source revision
    ↓
reproducible build
    ↓
focused install/update acceptance
    ↓
exact ZIP + SHA-256
    ↓
GitHub Release asset
    ↓
Joomla update XML
    ↓
native Joomla discovery/download/install
```

## Current update feeds

| Extension | Feed | Public status |
| --- | --- | --- |
| uddeIM Joomla 6 Enhanced | `updates/com_uddeim.xml` | `6.0.0-beta2` frozen candidate; Playwright package gate 1/1 PASS; publication pending |

More Joomla extensions can be added here later using the same release standard.

## Public release standard

Every extension distributed through this repository follows the same baseline.

A public release should be:

- installable through Joomla;
- clearly versioned;
- explicit about supported Joomla/PHP versions;
- test-backed;
- licensed correctly;
- attributed correctly;
- reproducible from a known source revision;
- integrity-verifiable;
- clearly marked as pre-release or stable;
- immutable once published;
- updateable through Joomla's native update mechanism when updates are offered.

The full reusable standard is documented in:

- `docs/PUBLIC_RELEASE_STANDARD.md`
- `docs/PUBLIC_RELEASE_CHECKLIST.md`
- `docs/RELEASE_POLICY.md`
- `docs/VERSIONING_POLICY.md`
- `docs/JOOMLA_COMPATIBILITY.md`

## Release integrity

Published release assets are treated as immutable.

For each package we aim to record at least:

- extension name;
- release version;
- source revision;
- package filename;
- byte size;
- SHA-256;
- tested Joomla/PHP compatibility;
- release status: pre-release or stable;
- focused acceptance evidence.

If a published package needs correction, a new version should be released rather
than silently replacing the existing asset.

## Compatibility policy

Compatibility claims are intentionally conservative.

A package is only advertised for Joomla/PHP combinations that have been tested
or otherwise explicitly accepted by the project release process.

For example, supporting Joomla 6.0 and 6.1 does not automatically mean that a
future Joomla 6.x minor is considered supported without a focused compatibility
gate.

## Provenance and attribution

Koelman Labs may distribute extensions that originated elsewhere and are being
maintained, modernized, ported, or continued for newer Joomla versions.

In those cases the original project history is preserved.

That means:

- original authors remain credited;
- existing copyright notices remain intact;
- contributor credits remain intact;
- bundled third-party licenses and attributions remain intact;
- Koelman Labs is identified as the current maintainer/distributor of the
  relevant release line, not as a replacement for the original authors.

An ownership transfer or official succession is only stated when such an
agreement actually exists.

## uddeIM Joomla 6 Enhanced

uddeIM is the first extension using this distribution foundation.

The original uddeIM project was maintained historically by **Stephan
Slabihoud**, with earlier work by **Benjamin Zweifel** and other contributors
credited in the source.

Koelman Labs maintains the **Joomla 6 Enhanced** compatibility, security,
testing, and distribution line.

The original authorship and project history are preserved.

Current release direction:

| Item | Status |
| --- | --- |
| Release line | `6.0.x` |
| Current candidate | `6.0.0-beta2` |
| First stable target | `6.0.0` |
| Joomla target | Joomla 6.0 / 6.1 |
| PHP target | PHP 8.3+ |
| Native update feed | Empty pending beta2 publication |
| Public beta release | `6.0.0-beta1` retained as immutable withdrawn prerelease |

Canonical uddeIM update feed:

```text
https://raw.githubusercontent.com/koelmanlabs/joomla-distribution/main/updates/com_uddeim.xml
```

The feed does not currently advertise a release. `6.0.0-beta1` remains published as an immutable withdrawn prerelease after Joomla-native testing proved a Windows ZIP path-separator packaging defect. `6.0.0-beta2` is now the frozen portable package candidate and has passed both the local forward-slash/extraction gate and the automated Playwright package gate (1/1 PASS), but it is not yet published. After the exact beta2 asset is published and its SHA-256 is recorded in the feed, it must still pass Joomla-native discovery/download/unpack/checksum/install acceptance from 5.6.3.

## For Joomla administrators

When a release is publicly available, administrators should be able to determine
from the release information:

- what the extension does;
- who originally created it;
- who currently maintains the release line;
- which Joomla/PHP versions are supported;
- whether it is stable or pre-release;
- how it is installed;
- how future updates are discovered;
- which license applies;
- how the downloaded package can be verified.

That is the public quality baseline for this repository.

## Repository principle

This repository is not intended to be a source dump or development workspace.

Its job is narrower:

> **publish Joomla extension releases in a way that is understandable,
> verifiable, test-backed, and reusable across multiple projects.**
