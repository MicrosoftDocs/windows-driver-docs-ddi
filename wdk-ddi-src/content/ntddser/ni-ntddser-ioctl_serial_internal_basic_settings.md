---
UID: NI:ntddser.IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS
title: IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS (ntddser.h)
description: The IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request sets a serial device to a basic operating mode.
old-location: serports\ioctl_serial_internal_basic_settings.htm
tech.root: serports
ms.assetid: 248b8682-b396-42b4-98f7-67191d98be1a
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS, IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS control, IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS control code [Serial Ports], ntddser/IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS, serports.ioctl_serial_internal_basic_settings, serref_86bdc0cd-4cfc-40de-82ac-81a088620e4c.xml
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddser.h
api_name:
- IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS IOCTL


## -description



The IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request sets a serial device to a basic operating mode. Serial's basic operating mode reads and writes one byte at a time, and does not use handshake flow control or time-outs. The basic operation mode is suitable for use by a driver that uses a subset of the 16550 UART interface. Examples of such drivers include a mouse driver or a graphics pad driver for older hardware that use a 16450 UART.

The IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request returns the operating mode settings that are in use just before Serial sets the basic operation mode. A client uses an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_internal_restore_settings">IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS</a> request to restore a previous operating mode. A client should treat the operating mode settings as opaque. Serial does not verify the settings when the settings are restored. Note also that a replacement driver for Serial might implement a different set of basic settings.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> points to a client-allocated SERIAL_BASIC_SETTINGS structure that Serial uses to output the current configuration.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> is set to the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of SERIAL_BASIC_SETTINGS. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. If <b>Status</b> is set to STATUS_BUFFER_TOO_SMALL, the value of <b>Parameters.DeviceIoControl.OutputLength</b> is less than the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_internal_restore_settings">IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS</a>
 

 

