# Raspberry Pi 5 CSI/MIPI Camera Bring-Up

## Goal
Bring up a CSI-2 camera on Raspberry Pi 5, validate the full
kernel → media controller → userspace pipeline, and document
issues relevant to future Android (AAOS) porting.

## Hardware
- Raspberry Pi 5 (8GB)
- Raspberry Pi Camera v3 (CSI-2)

## Software
- OS: Raspberry Pi OS (Bookworm)
- Kernel: 6.12.x (rpt)
- Firmware: vcgencmd version 2226a853 (release) (embedded)

## Platform Notes
- Raspberry Pi OS Bookworm uses /boot/firmware/config.txt for firmware configuration

## Hardware Arrival Execution Plan

### CSI Camera
1. Power off system
2. Attach ribbon (verify orientation)
3. Boot and capture dmesg probe logs
4. Verify /dev/media* and /dev/video*
5. Inspect media graph
6. Validate userspace capture

### USB-CAN
1. Verify USB enumeration
2. Bring up SocketCAN interface
3. Send/receive test frames
4. Integrate with vehicle state service

## Status
- [x] Platform baseline captured (kernel + firmware)
- [ ] CSI sensor probe confirmed (dmesg)
- [ ] Media controller graph captured (media-ctl)
- [ ] Userspace capture validated (libcamera)
- [ ] Failure mode testing
- [ ] Android/AAOS camera notes
