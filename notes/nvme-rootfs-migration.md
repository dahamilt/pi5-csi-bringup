## NVMe Root Filesystem Migration (Raspberry Pi 5)

### Initial State
- System booted kernel and root filesystem from SD card (`mmcblk0p2`)
- NVMe device (`nvme0n1`) detected but unused

### Procedure
1. Partitioned NVMe with GPT:
   - p1: 512MB FAT32 (boot)
   - p2: ext4 (root filesystem)

2. Copied root filesystem using `rsync`, excluding pseudo-filesystems:
   - `/proc`, `/sys`, `/dev`, `/run`, etc.

3. Copied boot firmware separately to avoid FAT32 symlink limitations.

4. Updated kernel boot parameters on NVMe:
   - Changed `root=PARTUUID=...` → `root=/dev/nvme0n1p2`

5. Updated Raspberry Pi boot order:
   - `raspi-config → Advanced Options → Boot Order → NVMe/USB`


###
During NVMe migration, mDNS hostname resolution failed.
Recovered system by manual ssh to various ips 
verified boot completion, and re-established network access.

### Networking Verification
- wlan0 acquired DHCP address: 192.168.0.217
- Default route via 192.168.0.1
- DNS provided via /etc/resolv.conf (NetworkManager-managed)
- mDNS (.local) temporarily unavailable during NVMe migration,
  but system reachable via IP-based SSH

