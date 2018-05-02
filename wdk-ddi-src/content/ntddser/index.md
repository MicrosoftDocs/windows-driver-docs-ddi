---
UID: NA:ntddser
ms.assetid: 1ef9acf8-d5d8-39b0-a68c-2a25e1e7e669
ms.author: windowsdriverdev
ms.date: 04/20/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddser.h header





This header is used by parports. For more information, see:

- [Parallel Ports](../_parports/index.md)

This section describes the I/O requests that are supported by the serial framework extension (SerCx) starting with Windows 8, and supported by the system-supplied Serial.sys driver starting with Windows 2000. For more information about SerCx and Serial.sys, see Serial Controller Drivers Overview.

SerCx is a system-supplied component that works in conjunction with a vendor-supplied serial controller driver to manage the hardware functions in a serial controller. A serial controller is a 16550 universal asynchronous receiver/transmitter (UART) or compatible device. The combination of SerCx and an extension-based serial controller driver typically support most of the I/O requests that are described in this section, but the specific set of I/O control requests supported depends on the implementation of the serial controller driver. For more information, see Serial I/O Request Interface.

Serial.sys is available as a system-supplied component in all supported versions of Windows. Serial.sys is a function driver for legacy serial devices and Plug and Play serial devices. It is also can be used as a lower-level device filter driver for Plug and Play devices that require a 16550 UART-compatible interface. The operation of Serial.sys as filter driver is identical to its operation as a function driver. Serial.sys implements the Serial system service. For more information, see Using Serial.sys and Serenum.sys.

The following subsections describe the I/O requests that are supported by SerCx and Serial.sys:

The following section describes the structure and constants that are used by serial device control requests:

The following subsection describes internal device control requests that are supported by Serial.sys, but not by SerCx:

The device-control signals and registers that are specified in this section are based on the hardware interface for a 16550 UART or compatible device. Examples of these device-control signals and registers include the ready-to-send control signal, the clear-to-send control signal, the line control register, and the modem status register.

For more information about the serial I/O requests that are defined for Windows, see the following:

- 
The IOCTL_SERIAL_XXX definitions in the Ntddser.h header file in the Windows Driver Kit (WDK).

- 
The Serial driver sample on GitHub.

- 
The Win32 communications functions documentation in the Windows SDK.


Send comments about this topic to Microsoft

