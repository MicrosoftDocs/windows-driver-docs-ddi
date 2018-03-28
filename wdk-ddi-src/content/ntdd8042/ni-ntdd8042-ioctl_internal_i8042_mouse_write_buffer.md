---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
title: IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a mouse device.
old-location: hid\ioctl_internal_i8042_mouse_write_buffer.htm
old-project: hid
ms.assetid: 40f6fd0b-8c18-408b-b1f7-5b280b9aa67d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER, IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER control code [Human Input Devices], hid.ioctl_internal_i8042_mouse_write_buffer, i8042ref_660499b1-32f5-4343-b0a2-176d03d0270c.xml, ntdd8042/IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
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
-	ntdd8042.h
api_name:
-	IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER
product: Windows
targetos: Windows
req.typenames: MOUSE_STATE, *PMOUSE_STATE
---

# IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER IOCTL


## -description



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

The <b>Status</b> member is set to one of the following values:




#### -STATUS_SUCCESS

The request completed successfully.


#### -STATUS_DEVICE_NOT_READY

The mouse interrupt is not initialized.


#### -STATUS_INVALID_PARAMETER

The input parameters are not valid.


#### -STATUS_IO_TIMEOUT

The request timed out.

