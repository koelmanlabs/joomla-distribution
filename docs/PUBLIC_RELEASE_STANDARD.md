# Koelman Labs Public Release Standard

This standard applies to every Joomla extension distributed publicly by Koelman Labs.

The goal is not Joomla Extensions Directory submission. The goal is that a public
package can be installed and maintained by an ordinary Joomla administrator
without access to the development environment or private project context.

## Core principles

A public release must be:

- installable;
- updateable through Joomla's native extension update mechanism when updates are provided;
- correctly versioned;
- explicit about Joomla and PHP compatibility;
- self-contained enough to understand and use;
- licensed and attributed correctly;
- reproducible from a known source revision;
- integrity-verifiable;
- clearly labelled as pre-release or stable;
- test-backed;
- immutable once published.

## Required package metadata

Every installable package must have:

- a valid Joomla extension manifest;
- a unique and correct extension element;
- an explicit extension version;
- correct extension type/client/group metadata;
- a meaningful name and description;
- license information;
- authorship/provenance information that does not misrepresent upstream work;
- a Joomla update-server entry when native updates are supported.

Manifest metadata, runtime version strings, update-feed version, release tag, and
release asset name must describe the same release.

## License and provenance

A public package must include the applicable license text when redistribution
requires it.

Existing copyright, attribution, and third-party license notices must be
preserved.

For maintained forks, ports, or compatibility lines:

- state the original project and authorship;
- state what Koelman Labs maintains;
- never imply an ownership transfer that did not happen;
- document material modifications where the applicable license requires this.

## Compatibility

Compatibility claims are evidence, not guesses.

For each public release, record at minimum:

- Joomla versions tested;
- PHP versions tested or minimum supported;
- relevant database target where applicable;
- upgrade path(s) tested;
- known unsupported combinations.

Do not claim all future Joomla minors merely because the same major version is
used.

## Packaging

The public ZIP must be the exact artifact that passed the release gate.

Before publication record:

- source repository and revision;
- package filename;
- package byte size;
- SHA-256;
- extension version;
- build command or build workflow;
- focused acceptance result.

Do not rebuild after acceptance and publish the new artifact under the old
checksum.

## Installation and update acceptance

A public release must prove the paths relevant to that extension.

Typical minimum gates:

1. clean install on an owned disposable Joomla environment;
2. same-version reinstall where supported;
3. upgrade from the supported previous release;
4. configuration/data preservation where applicable;
5. Joomla update-site registration;
6. native update discovery;
7. native download/install;
8. checksum validation when the feed supplies a checksum;
9. post-update functional smoke;
10. cleanup/rollback of the disposable test environment.

Extensions with destructive data migrations require additional migration and
rollback evidence.

## Public documentation

A public project must provide a human-readable landing page or README that says:

- what the extension does;
- who maintains it;
- provenance when based on earlier work;
- current stable/pre-release status;
- supported Joomla/PHP versions;
- how to install;
- how updates are delivered;
- where source code lives, when public;
- where to report issues or request support;
- license;
- known limitations that materially affect users.

Development-only paths, local usernames, private repository names, credentials,
and environment-specific secrets must not appear in public user documentation.

## Release channels

Pre-release labels such as alpha, beta, and RC are allowed, but must be explicit.

A pre-release:

- must not be described as stable;
- may be used to prove the public update pipeline;
- may have narrower compatibility claims;
- still requires correct licensing, provenance, package identity, and integrity metadata.

A stable release requires all blocking release gates to be green.

## Update feeds

Update feeds are public contracts.

Rules:

- never advertise a release asset that does not exist;
- use the correct Joomla extension identity;
- advertise only tested compatibility;
- use HTTPS;
- include SHA-256 when supported by the Joomla update format;
- keep old published versions immutable;
- correct mistakes by publishing a newer version, not by silently replacing assets;
- keep pre-release and stable semantics unambiguous.

## Security and privacy

A public release must not rely on insecure or undocumented outbound update
checks when Joomla's native update mechanism is available.

Any telemetry, remote requests, diagnostics, or data transmission must be
intentional and documented. Sensitive administrator/site information must not be
sent merely to check for updates.

Known security regressions block a stable release.

## Public-release decision

A release is publishable only when the release record can answer:

- What exactly is this package?
- What source revision produced it?
- What license applies?
- Who originally authored it and who maintains this release line?
- Which Joomla/PHP versions are actually supported?
- Has install/update been tested?
- How will Joomla discover future updates?
- Can the downloaded asset be verified?
- Is it clearly stable or pre-release?
- Where does a user go for documentation and issues?

If one of these cannot be answered truthfully, the release is not ready.
