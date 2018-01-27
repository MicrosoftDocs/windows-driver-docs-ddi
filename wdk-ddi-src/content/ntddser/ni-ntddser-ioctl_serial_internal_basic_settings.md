---
UID: NI:ntddser.IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS
title: IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS
author: windows-driver-content
description: The IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request sets a serial device to a basic operating mode.
old-location: serports\ioctl_serial_internal_basic_settings.htm
old-project: serports
ms.assetid: 248b8682-b396-42b4-98f7-67191d98be1a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_internal_basic_settings, IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS control code [Serial Ports], IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS, ntddser/IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS, serref_86bdc0cd-4cfc-40de-82ac-81a088620e4c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntddser.h
apiname: 
-	IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request sets a serial device to a basic operating mode. Serial's basic operating mode reads and writes one byte at a time, and does not use handshake flow control or time-outs. The basic operation mode is suitable for use by a driver that uses a subset of the 16550 UART interface. Examples of such drivers include a mouse driver or a graphics pad driver for older hardware that use a 16450 UART.

The IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request returns the operating mode settings that are in use just before Serial sets the basic operation mode. A client uses an <a href="..\ntddser\ni-ntddser-ioctl_serial_internal_restore_settings.md">IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS</a> request to restore a previous operating mode. A client should treat the operating mode settings as opaque. Serial does not verify the settings when the settings are restored. Note also that a replacement driver for Serial might implement a different set of basic settings.




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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of SERIAL_BASIC_SETTINGS. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. If <b>Status</b> is set to STATUS_BUFFER_TOO_SMALL, the value of <b>Parameters.DeviceIoControl.OutputLength</b> is less than the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_internal_restore_settings.md">IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

