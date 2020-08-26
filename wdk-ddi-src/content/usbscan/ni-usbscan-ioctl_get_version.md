---
UID: NI:usbscan.IOCTL_GET_VERSION
title: IOCTL_GET_VERSION (usbscan.h)
description: Returns the version number of the driver.
old-location: image\ioctl_get_version.htm
tech.root: image
ms.assetid: 0521cd73-a3ae-4c7e-b244-4477b69ffc6f
ms.date: 05/03/2018
keywords: ["IOCTL_GET_VERSION IOCTL"]
ms.keywords: IOCTL_GET_VERSION, IOCTL_GET_VERSION control, IOCTL_GET_VERSION control code [Imaging Devices], image.ioctl_get_version, stifnc_9ed7f2fc-763d-4090-8f25-e9a154055169.xml, usbscan/IOCTL_GET_VERSION
f1_keywords:
 - "usbscan/IOCTL_GET_VERSION"
 - "IOCTL_GET_VERSION"
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
- IOCTL_GET_VERSION
targetos: Windows
req.typenames: 
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

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_drv_version">DRV_VERSION</a> structure.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_get_version_si"></a><a id="DDK_IOCTL_GET_VERSION_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_GET_VERSION I/O control code, the caller must specify the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_drv_version">DRV_VERSION</a> structure as the function's <i>lpOutBuffer</i> parameter. The kernel-mode driver fills in the structure members.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



