# Joomla Compatibility Policy

Compatibility is explicit, conservative, and test-backed.

## uddeIM 6.0.x initial target

- Joomla: 6.0 and 6.1
- PHP: 8.3 or newer, subject to the Joomla 6 platform requirements
- Distribution: Joomla native extension update server
- Package source: GitHub Release asset

Initial update metadata should only match Joomla minors that have been tested.

Example policy:

```xml
<targetplatform name="joomla" version="6\.(0|1)" />
```

When a new Joomla minor is released, add it only after the focused compatibility/update gate is GREEN.

Compatibility metadata and the extension package manifest must not contradict each other.
