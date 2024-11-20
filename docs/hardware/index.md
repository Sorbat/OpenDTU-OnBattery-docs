# Getting Started

## Ready to Use

If you can afford it and assembling the parts from scratch is not utterly
important to you, you are encouraged to acquire an [OpenDTU
Fusion](../3rd_party/opendtu_fusion.md) board. It integrates both types of RF
modules together with one of the more powerful supported microcontrollers onto
a single ready-to-use board.

## Parts

OpenDTU-OnBattery supports the ESP32 family of microcontrollers. ESP32-S3
chips are preferred.

!!! note "Flash Memory"
    Due to the growing size of the firmware images, ESP32(-S3) boards with a
    minimum of 8 MB of flash memory are required in order to utilize
    over-the-air firmware updates. Most ESP32 boards provide only 4 MB of
    flash memory.

Depending on the inverter to be addressed, different RF modules are required.

- The HM series requires the [NRF24L01+](nrf24l01plus.md) module
- The HMS/HMT series requires the [CMT2300A](cmt2300a.md) module

Please see the [inverter overview](inverter_overview.md) to see if your inverter is supported and to determine the required RF module.

## Steps to build your own DTU

!!!note "Use of GPIOs"
    In general, ESP32 chips allow to use any function on any GPIO pin. There
    are a few restrictions, which are documented at the respective ESP32(-S3)
    DevKit subpages. Freely wire the logic pins between your ESP32(-S3) module
    and peripheral components. The important bit is to create and use a
    matching [device profile](../firmware/device_profiles.md).

1. Determine the [RF module(s)](inverter_overview.md) you need.
2. Get an [ESP32-S3 board](esp32s3_devkit.md).
3. Use a power supply with 5 V and 1 A. The USB cable connected to your PC or
   laptop may or may not provide sufficient power. Also the quality of the USB
   cable in use might have an impact.
4. Wire the ESP32-S3 to the RF module(s).
5. Wire a [display](display.md) (optional).
6. [Flash the firmware](../firmware/flash_esp.md) via USB.
7. Create, upload, and select a matching [device profile](../firmware/device_profiles.md)
   which describes your hardware (or look at a profile first and connect the
   logic pins accordingly).
