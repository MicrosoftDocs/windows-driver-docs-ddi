---
UID: NI:ntddser.IOCTL_SERIAL_SET_CHARS
title: IOCTL_SERIAL_SET_CHARS
author: windows-driver-content
description: The IOCTL_SERIAL_SET_CHARS request sets the special characters that the serial controller driver uses for handshake flow control. This driver verifies the specified special characters.
old-location: serports\ioctl_serial_set_chars.htm
old-project: serports
ms.assetid: f792bd01-19e1-4f15-917a-19ad46e7a4a9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_set_chars, IOCTL_SERIAL_SET_CHARS control code [Serial Ports], IOCTL_SERIAL_SET_CHARS, ntddser/IOCTL_SERIAL_SET_CHARS, serref_57af2187-3244-4b5d-a096-684050127a24.xml
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
-	Ntddser.h
apiname:
-	IOCTL_SERIAL_SET_CHARS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_CHARS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_SET_CHARS</b> request sets the special characters that the serial controller driver uses for handshake flow control. This driver verifies the specified special characters.

To obtain the special characters, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_chars.md">IOCTL_SERIAL_GET_CHARS</a> request.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <a href="..\ntddser\ns-ntddser-_serial_chars.md">SERIAL_CHARS</a> structure that is used to input special characters.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_CHARS</b> structure.


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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that <b>XoffChar</b> equals <b>XonChar</b>, or that one of them equals the handshake flow control escape character.


## -see-also

<a href="..\ntddser\ns-ntddser-_serial_chars.md">SERIAL_CHARS</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_chars.md">IOCTL_SERIAL_GET_CHARS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_SET_CHARS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

