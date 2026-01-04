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

## Status
- [x] Platform baseline captured (kernel + firmware)
- [ ] CSI sensor probe confirmed (dmesg)
- [ ] Media controller graph captured (media-ctl)
- [ ] Userspace capture validated (libcamera)
- [ ] Failure mode testing
- [ ] Android/AAOS camera notes
