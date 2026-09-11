# Koelman Labs — Joomla Distribution

Public distribution repository for Joomla extensions maintained by Koelman Labs.

## Purpose

This repository contains public release metadata for Joomla's native extension update system.

Development source may live in separate repositories. This repository is intentionally limited to distribution concerns such as:

- Joomla update XML feeds;
- public release metadata;
- compatibility policy;
- versioning policy;
- release policy.

Release packages are published as GitHub Release assets rather than committed to the Git tree.

## Update feeds

| Extension | Feed | Status |
| --- | --- | --- |
| uddeIM | `updates/com_uddeim.xml` | Foundation prepared; no release advertised yet |

## Repository contract

- Update feeds must never advertise a package that does not exist.
- Joomla compatibility must be explicit and tested before it is added to a feed.
- Release assets should be immutable for a published version.
- SHA-256 integrity metadata should be recorded for published packages.
- Development branches and private source repositories are not update endpoints.

See:

- `docs/RELEASE_POLICY.md`
- `docs/VERSIONING_POLICY.md`
- `docs/JOOMLA_COMPATIBILITY.md`
