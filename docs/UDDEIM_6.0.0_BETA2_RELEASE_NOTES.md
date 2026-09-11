# uddeIM 6.0.0 Beta 2

Corrected Joomla 6 Enhanced pre-release of uddeIM.

## Why Beta 2

Beta 1 was withdrawn from the Joomla update feed after native Joomla testing
proved that its Windows-built ZIP used backslashes in archive member paths.
The published Beta 1 asset remains immutable for audit/history.

Beta 2 uses a corrected portable ZIP builder and has passed the dedicated
package acceptance gate before publication.

## Compatibility

- Joomla 6.0 / 6.1
- PHP 8.3+

## Highlights

- Joomla 6 compatibility and hardening
- Joomla native extension update support
- Existing uddeIM configuration preserved during update/reinstall
- Legacy custom version checker retired
- Joomla update screen opens filtered to uddeIM
- Updated administrator About / release information
- GPL license included in the component package
- Original uddeIM authorship and contributor attribution preserved
- Portable ZIP member paths for Joomla-native archive extraction

## Package acceptance

```text
J60-ENH-UPDATE-GITHUB-001D-PKG
1/1 PASS

ZIP entries          1111
source files         1111
backslash entries    0
root manifest        1
package version      6.0.0-beta2
```

## Status

This is a pre-release intended for Joomla 6 update-pipeline and compatibility
validation.

After publication, the remaining release gate is Joomla-native discovery,
download, unpack, checksum validation, and installation from an installed
uddeIM 5.6.3 baseline.

## Integrity

Filename:

`com_uddeim-6.0.0-beta2-j6.zip`

Size:

`1732785 bytes`

SHA-256:

`33769b3e9f8942f2525e9cbf2c95d30f3f762f59a8759fc8aaf0926ef10418e0`
