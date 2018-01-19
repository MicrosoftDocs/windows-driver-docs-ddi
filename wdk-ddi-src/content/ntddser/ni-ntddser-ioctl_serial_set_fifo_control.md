---
UID: NI:ntddser.IOCTL_SERIAL_SET_FIFO_CONTROL
title: IOCTL_SERIAL_SET_FIFO_CONTROL
author: windows-driver-content
description: The IOCTL_SERIAL_SET_FIFO_CONTROL request sets the FIFO control register (FCR). Serial does not verify the specified FIFO control information.
old-location: serports\ioctl_serial_set_fifo_control.htm
old-project: serports
ms.assetid: b41a13a6-4573-495f-8dfd-9405917d8e66
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
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
req.alt-api: IOCTL_SERIAL_SET_FIFO_CONTROL
req.alt-loc: Ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_FIFO_CONTROL IOCTL



## -description
The <b>IOCTL_SERIAL_SET_FIFO_CONTROL</b> request sets the FIFO control register (FCR). Serial does not verify the specified FIFO control information.



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG that is used to input FIFO control information.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the size, in bytes, of a ULONG.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>.


## -remarks
