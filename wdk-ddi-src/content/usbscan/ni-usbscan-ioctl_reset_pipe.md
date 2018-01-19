---
UID: NI:usbscan.IOCTL_RESET_PIPE
title: IOCTL_RESET_PIPE
author: windows-driver-content
description: Resets the specified USB transfer pipe that is associated with the specified device handle.
old-location: image\ioctl_reset_pipe.htm
old-project: image
ms.assetid: aeca126a-449a-4a10-a4ce-1cd3939ac076
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _RAW_PIPE_TYPE, RAW_PIPE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_RESET_PIPE
req.alt-loc: Usbscan.h
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
req.typenames: RAW_PIPE_TYPE
req.product: Windows 10 or later.
---

# IOCTL_RESET_PIPE IOCTL



## -description

Resets the specified USB transfer pipe that is associated with the specified device handle.



Resets the specified USB transfer pipe that is associated with the specified device handle.



## -ioctlparameters

### -input-buffer
Pointer to a location that contains a value of type <a href="..\usbscan\ne-usbscan-pipe_type.md">PIPE_TYPE</a>.


### -input-buffer-length
Size of the input buffer.


### -output-buffer
<b>NULL</b>.


### -output-buffer-length
Zero.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


Device handle, obtained by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a>.

IOCTL_RESET_PIPE

Pointer to a location that contains a value of type <a href="..\usbscan\ne-usbscan-pipe_type.md">PIPE_TYPE</a>.

Size of the input buffer.

NULL

Zero.

Pointer to a location to receive the number of bytes returned.

Optional pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

When the <b>DeviceloControl</b> function is called with the IOCTL_RESET_PIPE I/O control code, the caller must specify one of the <a href="..\usbscan\ne-usbscan-pipe_type.md">PIPE_TYPE</a>-typed values as the function's <i>lpInBuffer</i> parameter. This value indicates on which of the transfer pipes (interrupt, bulk IN, bulk OUT) the operation should be performed. For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.</p>