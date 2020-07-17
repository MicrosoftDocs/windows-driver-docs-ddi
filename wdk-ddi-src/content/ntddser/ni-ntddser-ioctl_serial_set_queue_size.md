---
UID: NI:ntddser.IOCTL_SERIAL_SET_QUEUE_SIZE
title: IOCTL_SERIAL_SET_QUEUE_SIZE (ntddser.h)
description: The IOCTL_SERIAL_SET_QUEUE_SIZE request sets the size of the internal receive buffer. If the requested size is greater than the current receive buffer size, a new receive buffer is created. Otherwise, the receive buffer is not changed.
old-location: serports\ioctl_serial_set_queue_size.htm
tech.root: serports
ms.assetid: 532dfe17-c901-4fc5-90d4-d300aa0e5720
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_SET_QUEUE_SIZE IOCTL"]
ms.keywords: IOCTL_SERIAL_SET_QUEUE_SIZE, IOCTL_SERIAL_SET_QUEUE_SIZE control, IOCTL_SERIAL_SET_QUEUE_SIZE control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_QUEUE_SIZE, serports.ioctl_serial_set_queue_size, serref_52ce370d-5e55-4a48-a7d2-87da706bb4e7.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_SET_QUEUE_SIZE"
 - "IOCTL_SERIAL_SET_QUEUE_SIZE"
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
- Ntddser.h
api_name:
- IOCTL_SERIAL_SET_QUEUE_SIZE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_QUEUE_SIZE IOCTL


## -description


The <b>IOCTL_SERIAL_SET_QUEUE_SIZE</b> request sets the size of the internal receive buffer. If the requested size is greater than the current receive buffer size, a new receive buffer is created. Otherwise, the receive buffer is not changed.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_queue_size">SERIAL_QUEUE_SIZE</a> structure that is used to input a receive buffer size.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_QUEUE_SIZE</b> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_queue_size">SERIAL_QUEUE_SIZE</a>
 

 

