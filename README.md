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

## Current Status
- [x] Kernel and firmware validated
- [ ] CSI sensor probe
- [ ] Media controller graph validated
- [ ] Userspace capture
- [ ] Failure mode testing
- [ ] Android relevance notes
