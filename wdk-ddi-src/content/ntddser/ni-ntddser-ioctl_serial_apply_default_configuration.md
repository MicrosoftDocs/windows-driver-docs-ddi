---
UID: NI:ntddser.IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
title: IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION (ntddser.h)
description: The IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code configures the serial port to use the default hardware settings for the serial controller device.
old-location: serports\ioctl_serial_apply_default_configuration.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION IOCTL"]
ms.keywords: IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION, IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control, IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code [Serial Ports], ntddser/IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION, serports.ioctl_serial_apply_default_configuration
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
 - ntddser/IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
---

# IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION IOCTL


## -description

The <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> control code configures the serial port to use the default hardware settings for the serial controller device. These settings are obtained from the ACPI resource descriptor for the serial controller device. For more information, see the [ACPI 5.0 specification](https://uefi.org/specifications).

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">generic status values for serial device control requests</a>. A status of STATUS_NOT_IMPLEMENTED indicates that the serial port does not support a default configuration. In this case, the client must use the other <b>IOCTL_SERIAL_<i>XXX</i></b> I/O control requests to explicitly configure the serial port.

## -remarks

The client (application or peripheral device driver) sends this IOCTL to configure the serial port to use a set of default connection settings. These settings include connection-specific hardware parameters such as the baud rate, time-out values, and flow-control flags.

This IOCTL is supported by versions 1 and 2 of the serial framework extension (SerCx and SerCx2). Serial.sys, which manages the named serial ports (COM1, COM2, and so on) on a PC, does not support this IOCTL.

If a serial port does not support this IOCTL, the client must explicitly specify the connection settings for the port. That is, the client must send an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_baud_rate">IOCTL_SERIAL_SET_BAUD_RATE</a> request to set the baud rate, send an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_timeouts">IOCTL_SERIAL_SET_TIMEOUTS</a> request to set the time-out intervals, and so on.

Immediately after a client opens a serial port, the client should assume that the port is configured in an unknown, uninitialized state rather than in some known, default state.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_baud_rate">IOCTL_SERIAL_SET_BAUD_RATE</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_timeouts">IOCTL_SERIAL_SET_TIMEOUTS</a>
