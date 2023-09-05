# CYW920829-VR BSP

## Overview

The AIROC™ CYW20829 Bluetooth® LE SoC is a Bluetooth® 5.4 core spec-compliant for IoT, HID, smart home and industrial applications. It comes with the right combination of low power and high performance dual core Arm® Cortex® M33 to meet the high demands of Bluetooth® LE Applications.



To use code from the BSP, simply include a reference to `cybsp.h`.

## Features

### Kit Features:

* 32-bit CPU subsystem with Arm® Cortex® M33
* 256-KB SRAM with power and data retention control
* Low power 1.7 - 3.6 V operation
* ADCMic with Audio and DC measurement capability
* Connectors for battery
* 10-pin SWD connectors
* Up to 26 programmable GPIOs

## BSP Configuration

The BSP has a few hooks that allow its behavior to be configured. Some of these items are enabled by default while others must be explicitly enabled. Items enabled by default are specified in the CYW920829-VR.mk file. The items that are enabled can be changed by creating a custom BSP or by editing the application makefile.

Components:
* Device specific category reference (e.g.: CAT1) - This component, enabled by default, pulls in any device specific code for this board.

Defines:
* CYBSP_WIFI_CAPABLE - This define, disabled by default, causes the BSP to initialize the interface to an onboard wireless chip if it has one.
* CY_USING_HAL - This define, enabled by default, specifies that the HAL is intended to be used by the application. This will cause the BSP to include the applicable header file and to initialize the system level drivers.
* CYBSP_CUSTOM_SYSCLK_PM_CALLBACK - This define, disabled by default, causes the BSP to skip registering its default SysClk Power Management callback, if any, and instead to invoke the application-defined function `cybsp_register_custom_sysclk_pm_callback` to register an application-specific callback.

### Clock Configuration

| Clock    | Source    | Output Frequency |
|----------|-----------|------------------|
| FLL      | IHO       | 96.0 MHz         |
| CLK_HF0  | CLK_PATH0 | 96 MHz           |
| CLK_HF1  | CLK_PATH0 | 96 MHz           |
| CLK_HF2  | CLK_PATH2 | 48 MHz           |
| CLK_HF3  | CLK_PATH1 | 24 MHz           |

### Power Configuration

* System Active Power Mode: LP
* System Idle Power Mode: Deep Sleep
* VDDA Voltage: 3300 mV
* VDDD Voltage: 3300 mV

See the [BSP Setttings][settings] for additional board specific configuration settings.

## API Reference Manual

The CYW920829-VR Board Support Package provides a set of APIs to configure, initialize and use the board resources.

See the [BSP API Reference Manual][api] for the complete list of the provided interfaces.

## More information
* [CYW920829-VR BSP API Reference Manual][api]
* [CYW920829-VR Documentation](https://www.infineon.com/cms/en/product/promopages/airoc20829/)
* [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)
* [Infineon GitHub](https://github.com/infineon)
* [ModusToolbox™](https://www.cypress.com/products/modustoolbox-software-environment)

[api]: https://infineon.github.io/TARGET_CYW920829-VR/html/modules.html
[settings]: https://infineon.github.io/TARGET_CYW920829-VR/html/md_bsp_settings.html

---
© Cypress Semiconductor Corporation (an Infineon company) or an affiliate of Cypress Semiconductor Corporation, 2019-2022.