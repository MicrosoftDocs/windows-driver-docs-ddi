---
UID: NI:usbscan.IOCTL_GET_CHANNEL_ALIGN_RQST
title: IOCTL_GET_CHANNEL_ALIGN_RQST (usbscan.h)
description: Returns a USB device's maximum packet size for the read, write, and interrupt transfer pipes associated with the specified device handle.
old-location: image\ioctl_get_channel_align_rqst.htm
tech.root: image
ms.assetid: 8025a092-470a-4cd5-af63-21f82e094933
ms.date: 05/03/2018
keywords: ["IOCTL_GET_CHANNEL_ALIGN_RQST IOCTL"]
ms.keywords: IOCTL_GET_CHANNEL_ALIGN_RQST, IOCTL_GET_CHANNEL_ALIGN_RQST control, IOCTL_GET_CHANNEL_ALIGN_RQST control code [Imaging Devices], image.ioctl_get_channel_align_rqst, stifnc_a81e47eb-3d6f-4bfb-a371-08c42602bc5a.xml, usbscan/IOCTL_GET_CHANNEL_ALIGN_RQST
f1_keywords:
 - "usbscan/IOCTL_GET_CHANNEL_ALIGN_RQST"
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
- IOCTL_GET_CHANNEL_ALIGN_RQST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GET_CHANNEL_ALIGN_RQST IOCTL


## -description



Returns a USB device's maximum packet size for the read, write, and interrupt transfer pipes associated with the specified device handle.




## -ioctlparameters




### -input-buffer

<b>NULL</b>.


### -input-buffer-length

Zero.


### -output-buffer

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_channel_info">CHANNEL_INFO</a> structure.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_get_channel_align_rqst_si"></a><a id="DDK_IOCTL_GET_CHANNEL_ALIGN_RQST_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_GET_CHANNEL_ALIGN_RQST I/O control code, the caller must specify the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_channel_info">CHANNEL_INFO</a> structure as the function's <i>lpOutBuffer</i> parameter. The kernel-mode driver fills in the structure.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



