# Joomla Compatibility Policy

Compatibility is explicit, conservative, and test-backed for every extension.

## General rules

For each extension/release, record:

- Joomla versions actually tested;
- PHP minimum/tested versions;
- relevant database constraints;
- install and upgrade paths tested;
- known unsupported combinations.

Initial update metadata should only match Joomla versions that have passed the
focused compatibility/update gate.

When a new Joomla minor is released, add it only after focused acceptance is
GREEN.

Compatibility metadata, package manifest documentation, and public README must
not contradict one another.

## Update feed example

A project that has proven Joomla 6.0 and 6.1, but not later minors, can use:

```xml
<targetplatform name="joomla" version="6\.(0|1)" />
```

Do not broaden this regex merely because a future Joomla 6 minor exists.

## uddeIM 6.0.x current target

- Joomla: 6.0 and 6.1;
- PHP: 8.3 or newer, subject to Joomla platform requirements;
- distribution: Joomla native extension update server;
- package source: immutable GitHub Release asset.
