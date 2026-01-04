# Android Camera Stack Notes (Pre-Bring-Up)

## Linux side
- CSI camera exposed via V4L2
- Media controller graph defines pipeline
- Sensor controlled over I2C, data over CSI-2

## Android side (expected gaps)
- libcamera not present in AOSP
- Camera HAL required to bridge V4L2 → framework
- Likely vendor HAL or external provider
- SELinux + init service implications

## Questions to answer later
- V4L2 HAL vs custom provider?
- Where does ISP live in Android pipeline?
