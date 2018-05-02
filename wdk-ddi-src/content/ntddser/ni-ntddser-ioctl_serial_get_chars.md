---
UID: NI:ntddser.IOCTL_SERIAL_GET_CHARS
title: IOCTL_SERIAL_GET_CHARS
author: windows-driver-content
description: The IOCTL_SERIAL_GET_CHARS request retrieves the special characters that the serial controller driver uses with handshake flow control. The special characters are described by a SERIAL_CHARS structure.
old-location: serports\ioctl_serial_get_chars.htm
old-project: serports
ms.assetid: f8ebf57a-1d2f-4362-8713-c37b6ef62cb6
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_GET_CHARS, IOCTL_SERIAL_GET_CHARS control, IOCTL_SERIAL_GET_CHARS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_CHARS, serports.ioctl_serial_get_chars, serref_103c18cc-6260-4a9d-8f2f-01ef8b82aebe.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_GET_CHARS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_GET_CHARS IOCTL


## -description


The <b>IOCTL_SERIAL_GET_CHARS</b> request retrieves the special characters that the serial controller driver uses with handshake flow control. The special characters are described by a <a href="https://msdn.microsoft.com/library/windows/hardware/jj673020">SERIAL_CHARS</a> structure.

To set special characters, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546688">IOCTL_SERIAL_SET_CHARS</a> request.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_CHARS</b> structure that the serial controller driver uses to output the special characters.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a <b>SERIAL_CHARS</b> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of <b>SERIAL_CHARS</b>. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546688">IOCTL_SERIAL_SET_CHARS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj673020">SERIAL_CHARS</a>
 

 

