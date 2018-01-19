---
UID: NI:usbscan.IOCTL_SET_TIMEOUT
title: IOCTL_SET_TIMEOUT
author: windows-driver-content
description: Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.
old-location: image\ioctl_set_timeout.htm
old-project: image
ms.assetid: 90403ef3-d86c-4e2b-842d-c121cce07a47
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
req.alt-api: IOCTL_SET_TIMEOUT
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

# IOCTL_SET_TIMEOUT IOCTL



## -description
Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.



## -ioctlparameters

### -input-buffer
Pointer to a <a href="..\usbscan\ns-usbscan-_usbscan_timeout.md">USBSCAN_TIMEOUT</a> structure.


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

IOCTL_SET_TIMEOUT

Pointer to a <a href="..\usbscan\ns-usbscan-_usbscan_timeout.md">USBSCAN_TIMEOUT</a> structure.

Size of the input buffer.

<b>NULL</b>.

Zero.

Pointer to a location to receive the number of bytes written.

Optional pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

When the <b>DeviceloControl</b> function is called with the IOCTL_SET_TIMEOUT I/O control code, the caller must specify the address of a <a href="..\usbscan\ns-usbscan-_usbscan_timeout.md">USBSCAN_TIMEOUT</a> structure as the function's <i>lpInBuffer</i> parameter.

Using the USBSCAN_TIMEOUT structure's contents, the kernel-mode driver resets the time-out value for each type of operation: bulk IN read, bulk OUT write, or interrupt.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

The IOCTL_SET_TIMEOUT I/O control code is available in Microsoft Windows Me, Windows XP and later operating systems versions.</p>