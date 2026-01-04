## Device Tree Notes
- Live DT dumped via /proc/device-tree
- CSI nodes to inspect once camera attached (i2c, unicam, isp)

## Kernel config access
- /proc/config.gz not present (IKCONFIG_PROC likely disabled); using /boot/firmware config-* or /lib/modules/.../build/.config instead.
