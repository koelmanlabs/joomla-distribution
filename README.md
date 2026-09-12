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
| uddeIM Joomla 6 Enhanced | `updates/com_uddeim.xml` | `6.0.0` stable published, advertised, and final native updater acceptance CLOSED GREEN |

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
| Current stable release | `6.0.0` |
| First stable target | `6.0.0` — achieved |
| Joomla target | Joomla 6.0 / 6.1 |
| PHP target | PHP 8.3+ |
| Native update feed | Stable `6.0.0` advertised; final stable native updater acceptance CLOSED GREEN |
| Public releases | `6.0.0` stable published; `6.0.0-beta2` retained as accepted prerelease; `6.0.0-beta1` retained as immutable withdrawn prerelease |

Canonical uddeIM update feed:

```text
https://raw.githubusercontent.com/koelmanlabs/joomla-distribution/main/updates/com_uddeim.xml
```

The update feed now advertises the exact stable `6.0.0` release asset. The frozen stable package passed exact-package portability, focused install/config-preservation acceptance, the final full canonical regression at **98/98 PASS** on Joomla 6.1.2, and the final Joomla-native public updater acceptance from an official uddeIM 5.6.3 baseline. `6.0.0-beta2` remains published as the accepted prerelease that previously proved the public Joomla-native updater path; `6.0.0-beta1` remains an immutable withdrawn prerelease after its Windows ZIP path-separator packaging defect.

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


## Native updater acceptance

uddeIM 6.0.0-beta2 has now passed the Joomla-native update path from an
installed uddeIM 5.6.3 baseline on the disposable Joomla 6.1.2 acceptance clone.

Verified:

- public feed discovery;
- exact GitHub Release asset;
- portable ZIP unpack;
- checksum acceptance;
- Joomla component update;
- extension version 6.0.0-beta2;
- extension ID preservation;
- exact pre-update config backup;
- semantic configuration preservation with zero mismatches;
- processed update row removal;
- enabled Koelman Labs update feed after update;
- post-update administrator runtime health.

The automated non-destructive post-state gate
`J60-ENH-UPDATE-GITHUB-001D-POST` passed 1/1 in 5.7s.

The promotion/stable full canonical regression is complete at **98/98 PASS**
against uddeIM 6.0.0. The final Joomla-native public updater acceptance from
an official uddeIM 5.6.3 baseline is also CLOSED GREEN. The destructive update
completed successfully; its only RED assertion was a fixture-only duplicate
update-site mapping, classified TEST HARNESS. A non-destructive post-state gate
then passed 1/1 and confirmed version 6.0.0, schema 5.6, cleared update rows,
config backup/preservation, and healthy administrator runtime.

## Stable 6.0.0 final native updater acceptance

The final stable acceptance used a fresh disposable Joomla 6.1.2 clone with the
exact official upstream uddeIM 5.6.3 component installed cleanly.

The real Joomla-native update pipeline then completed:

```text
5.6.3 -> public Koelman Labs stable feed -> 6.0.0
extension id   387 preserved
schema         5.6 preserved
update rows    cleared
package bytes  1732775
package sha256 f4e79efb182a9ff3b51e4a971607a374764d258d501622d9164d630e95e7fc7d
```

The destructive test stopped only on a fixture-side assertion that expected one
update-site mapping while the disposable clone contained two rows pointing to
the same enabled Koelman Labs feed. This was classified **TEST HARNESS /
FIXTURE CONTAMINATION**. The updater was not rerun.

The dedicated non-destructive closure gate
`J60-ENH-UPDATE-GITHUB-001E-PUBLIC-POST` passed 1/1 in 5.0s and confirmed the
successful 6.0.0 post-state.

Public stable verdict: **FINAL / CLOSED GREEN**.
