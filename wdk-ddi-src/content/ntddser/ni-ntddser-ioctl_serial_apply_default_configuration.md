---
UID: NI:ntddser.IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
title: IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
author: windows-driver-content
description: The IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code configures the serial port to use the default hardware settings for the serial controller device.
old-location: serports\ioctl_serial_apply_default_configuration.htm
old-project: serports
ms.assetid: 59AA6029-906C-480F-8F18-82C271A2BE88
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_apply_default_configuration, IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code [Serial Ports], IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION, ntddser/IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddser.h
apiname:
-	IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> control code configures the serial port to use the default hardware settings for the serial controller device. These settings are obtained from the ACPI resource descriptor for the serial controller device. For more information, see the <i>Advanced Configuration and Power Interface Specification, Revision 5.0</i>, at the <a href="http://www.acpi.info">ACPI</a> website.




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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">generic status values for serial device control requests</a>. A status of STATUS_NOT_IMPLEMENTED indicates that the serial port does not support a default configuration. In this case, the client must use the other <b>IOCTL_SERIAL_<i>XXX</i></b> I/O control requests to explicitly configure the serial port.


## -remarks


The client (application or peripheral device driver) sends this IOCTL to configure the serial port to use a set of default connection settings. These settings include connection-specific hardware parameters such as the baud rate, time-out values, and flow-control flags.

This IOCTL is supported by versions 1 and 2 of the serial framework extension (SerCx and SerCx2). Serial.sys, which manages the named serial ports (COM1, COM2, and so on) on a PC, does not support this IOCTL.

If a serial port does not support this IOCTL, the client must explicitly specify the connection settings for the port. That is, the client must send an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_baud_rate.md">IOCTL_SERIAL_SET_BAUD_RATE</a> request to set the baud rate, send an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a> request to set the time-out intervals, and so on.

Immediately after a client opens a serial port, the client should assume that the port is configured in an unknown, uninitialized state rather than in some known, default state.



## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_baud_rate.md">IOCTL_SERIAL_SET_BAUD_RATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

