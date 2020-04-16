---
UID: NI:usbscan.IOCTL_RESET_PIPE
title: IOCTL_RESET_PIPE (usbscan.h)
description: Resets the specified USB transfer pipe that is associated with the specified device handle.
old-location: image\ioctl_reset_pipe.htm
tech.root: image
ms.assetid: aeca126a-449a-4a10-a4ce-1cd3939ac076
ms.date: 05/03/2018
keywords: ["IOCTL_RESET_PIPE IOCTL"]
ms.keywords: IOCTL_RESET_PIPE, IOCTL_RESET_PIPE control, IOCTL_RESET_PIPE control code [Imaging Devices], image.ioctl_reset_pipe, stifnc_907d0aea-158a-4219-9235-85a16d6da30f.xml, usbscan/IOCTL_RESET_PIPE
f1_keywords:
 - "usbscan/IOCTL_RESET_PIPE"
req.header: usbscan.h
req.include-header: Usbscan.h
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
- Usbscan.h
api_name:
- IOCTL_RESET_PIPE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_RESET_PIPE IOCTL


## -description



Resets the specified USB transfer pipe that is associated with the specified device handle.




## -ioctlparameters




### -input-buffer

Pointer to a location that contains a value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ne-usbscan-pipe_type">PIPE_TYPE</a>.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

<b>NULL</b>.


### -output-buffer-length

Zero.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_reset_pipe_si"></a><a id="DDK_IOCTL_RESET_PIPE_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_RESET_PIPE I/O control code, the caller must specify one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ne-usbscan-pipe_type">PIPE_TYPE</a>-typed values as the function's <i>lpInBuffer</i> parameter. This value indicates on which of the transfer pipes (interrupt, bulk IN, bulk OUT) the operation should be performed. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



