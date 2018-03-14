---
UID: NI:ntddser.IOCTL_SERIAL_SET_QUEUE_SIZE
title: IOCTL_SERIAL_SET_QUEUE_SIZE
author: windows-driver-content
description: The IOCTL_SERIAL_SET_QUEUE_SIZE request sets the size of the internal receive buffer. If the requested size is greater than the current receive buffer size, a new receive buffer is created. Otherwise, the receive buffer is not changed.
old-location: serports\ioctl_serial_set_queue_size.htm
old-project: serports
ms.assetid: 532dfe17-c901-4fc5-90d4-d300aa0e5720
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_QUEUE_SIZE, IOCTL_SERIAL_SET_QUEUE_SIZE control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_QUEUE_SIZE, serports.ioctl_serial_set_queue_size, serref_52ce370d-5e55-4a48-a7d2-87da706bb4e7.xml
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
-	IOCTL_SERIAL_SET_QUEUE_SIZE
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_QUEUE_SIZE IOCTL


## -description


The <b>IOCTL_SERIAL_SET_QUEUE_SIZE</b> request sets the size of the internal receive buffer. If the requested size is greater than the current receive buffer size, a new receive buffer is created. Otherwise, the receive buffer is not changed.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <a href="..\ntddser\ns-ntddser-_serial_queue_size.md">SERIAL_QUEUE_SIZE</a> structure that is used to input a receive buffer size.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_QUEUE_SIZE</b> structure.


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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also

<a href="..\ntddser\ns-ntddser-_serial_queue_size.md">SERIAL_QUEUE_SIZE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_SET_QUEUE_SIZE control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

