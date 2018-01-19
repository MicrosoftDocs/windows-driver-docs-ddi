---
UID: NI:usbscan.IOCTL_GET_VERSION
title: IOCTL_GET_VERSION
author: windows-driver-content
description: Returns the version number of the driver.
old-location: image\ioctl_get_version.htm
old-project: image
ms.assetid: 0521cd73-a3ae-4c7e-b244-4477b69ffc6f
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
req.alt-api: IOCTL_GET_VERSION
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

# IOCTL_GET_VERSION IOCTL



## -description
Returns the version number of the driver.



## -ioctlparameters

### -input-buffer
<b>NULL</b>


### -input-buffer-length
Zero.


### -output-buffer
Pointer to a <a href="..\usbscan\ns-usbscan-_drv_version.md">DRV_VERSION</a> structure.


### -output-buffer-length
Size of the output buffer.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


Device handle, obtained by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a>.

IOCTL_GET_VERSION

<b>NULL</b>

Zero.

Pointer to a <a href="..\usbscan\ns-usbscan-_drv_version.md">DRV_VERSION</a> structure.

Size of the output buffer.

Pointer to a location to receive the number of bytes returned.

Optional pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

When the <b>DeviceloControl</b> function is called with the IOCTL_GET_VERSION I/O control code, the caller must specify the address of a <a href="..\usbscan\ns-usbscan-_drv_version.md">DRV_VERSION</a> structure as the function's <i>lpOutBuffer</i> parameter. The kernel-mode driver fills in the structure members.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.</p>