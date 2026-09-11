# Public Release Checklist

Use this checklist for every Koelman Labs Joomla extension before publishing a
GitHub Release asset or advertising it in a Joomla update feed.

## Identity

- [ ] Extension name is correct.
- [ ] Joomla element/type/client/group are correct.
- [ ] Manifest version is the intended release version.
- [ ] Runtime/display version matches the manifest.
- [ ] Release tag/title/asset filename use the same version.

## Provenance and license

- [ ] Original authorship is preserved.
- [ ] Koelman Labs maintenance role is described accurately.
- [ ] Main license is stated.
- [ ] Required license text is included in the public package.
- [ ] Bundled third-party licenses/credits are retained.

## Documentation

- [ ] README explains purpose.
- [ ] README states stable/pre-release status.
- [ ] Tested Joomla/PHP compatibility is stated.
- [ ] Install instructions are present.
- [ ] Update mechanism is documented.
- [ ] Issue/support location is documented.
- [ ] Known material limitations are documented.
- [ ] No private/local-only information is exposed.

## Build and artifact identity

- [ ] Build source revision recorded.
- [ ] Reproducible build command/workflow recorded.
- [ ] Package structure validated.
- [ ] Exact byte size recorded.
- [ ] Exact SHA-256 recorded.
- [ ] Published asset is byte-for-byte the accepted artifact.

## Acceptance

- [ ] Clean install gate passes.
- [ ] Relevant upgrade gate passes.
- [ ] Configuration/data preservation passes where applicable.
- [ ] Joomla update-site registration passes.
- [ ] Native update discovery passes.
- [ ] Native update download/install passes.
- [ ] Post-update smoke passes.
- [ ] Disposable environment is restored/cleaned.

## Distribution

- [ ] GitHub release status is correct: pre-release or stable.
- [ ] Release asset exists before feed publication.
- [ ] Update feed points to the exact asset.
- [ ] Compatibility metadata matches tested evidence.
- [ ] SHA-256 in metadata matches the published asset.
- [ ] Published version/asset will not be silently replaced.

## Stable-only gates

- [ ] No known blocking security regression.
- [ ] No known blocking privacy issue.
- [ ] No legacy update path contradicts the native update mechanism.
- [ ] Administrator About/version information is accurate.
- [ ] Public documentation is current.
