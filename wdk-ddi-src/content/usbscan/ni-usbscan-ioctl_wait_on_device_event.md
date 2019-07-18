---
UID: NI:usbscan.IOCTL_WAIT_ON_DEVICE_EVENT
title: IOCTL_WAIT_ON_DEVICE_EVENT (usbscan.h)
description: Returns information about an event occurring on a USB interrupt pipe.
old-location: image\ioctl_wait_on_device_event.htm
tech.root: image
ms.assetid: 0895a19b-bb28-405a-98df-28522a18ec2b
ms.date: 05/03/2018
ms.keywords: IOCTL_WAIT_ON_DEVICE_EVENT, IOCTL_WAIT_ON_DEVICE_EVENT control, IOCTL_WAIT_ON_DEVICE_EVENT control code [Imaging Devices], image.ioctl_wait_on_device_event, stifnc_ef4b6e5f-ed60-4354-adae-443e1a27b215.xml, usbscan/IOCTL_WAIT_ON_DEVICE_EVENT
ms.topic: ioctl
f1_keywords:
 - "usbscan/IOCTL_WAIT_ON_DEVICE_EVENT"
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
- IOCTL_WAIT_ON_DEVICE_EVENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_WAIT_ON_DEVICE_EVENT IOCTL


## -description


Returns information about an event occurring on a USB interrupt pipe.


## -ioctlparameters




### -input-buffer

<b>NULL</b>


### -input-buffer-length

Zero.


### -output-buffer

Pointer to a buffer that is large enough to receive the largest packet the device is capable of sending on the interrupt pipe.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_wait_on_device_event_si"></a><a id="DDK_IOCTL_WAIT_ON_DEVICE_EVENT_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_WAIT_ON_DEVICE_EVENT control code, the caller must specify a buffer pointer as the function's <i>lpOutBuffer</i> parameter. The buffer must be large enough to hold the largest packet the device can send on its interrupt pipe.

The type and size of information returned are device-specific. For example, a still image device might issue an interrupt when a user presses one of its buttons, and the return packet might indicate which button was pressed.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



