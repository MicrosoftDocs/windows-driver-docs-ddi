---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
title: IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a mouse device.
old-location: hid\ioctl_internal_i8042_mouse_write_buffer.htm
old-project: hid
ms.assetid: 40f6fd0b-8c18-408b-b1f7-5b280b9aa67d
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _MOUSE_STATE, MOUSE_STATE, *PMOUSE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
req.alt-loc: ntdd8042.h
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
req.typenames: MOUSE_STATE, *PMOUSE_STATE
---

# IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER IOCTL



## -description

The IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a mouse device. An upper-level filter driver can use this request to control the operation of a mouse.

I8042prt synchronizes write buffer requests with one another. I8042prt synchronizes the actual write of data with the mouse ISR.



The IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a mouse device. An upper-level filter driver can use this request to control the operation of a mouse.

I8042prt synchronizes write buffer requests with one another. I8042prt synchronizes the actual write of data with the mouse ISR.



## -ioctlparameters

### -input-buffer
<b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to a client-allocated buffer that supplies the data to write to an i8042 port controller.


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the number of bytes in the input buffer, which must be greater than 1.


### -output-buffer
None


### -output-buffer-length
None


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Status</b> member is set to one of the following values:



The request completed successfully.

The mouse interrupt is not initialized.

The input parameters are not valid.

The request timed out.


## -remarks
