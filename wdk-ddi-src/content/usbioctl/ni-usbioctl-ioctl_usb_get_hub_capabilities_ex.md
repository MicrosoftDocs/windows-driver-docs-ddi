---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_CAPABILITIES_EX
title: IOCTL_USB_GET_HUB_CAPABILITIES_EX
author: windows-driver-content
description: The IOCTL_USB_GET_HUB_CAPABILITIES_EX I/O control request retrieves the capabilities of a USB hub.IOCTL_USB_GET_HUB_CAPABILITIES_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).
old-location: buses\ioctl_usb_get_hub_capabilities_ex.htm
old-project: usbref
ms.assetid: 49c25f30-8eff-4894-8a82-a90c5a7d9aa4
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_USB_GET_HUB_CAPABILITIES_EX, IOCTL_USB_GET_HUB_CAPABILITIES_EX control, IOCTL_USB_GET_HUB_CAPABILITIES_EX control code [Buses], buses.ioctl_usb_get_hub_capabilities_ex, usbioctl/IOCTL_USB_GET_HUB_CAPABILITIES_EX, usbirp_bed6a9f5-00ee-4f0b-9906-cd27d85a74c2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later.
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
-	Usbioctl.h
api_name:
-	IOCTL_USB_GET_HUB_CAPABILITIES_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_HUB_CAPABILITIES_EX IOCTL


## -description



The <b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> I/O control request retrieves the capabilities of a USB hub.

<b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated buffer.


### -input-buffer-length

 The buffer length equals <code>sizeof(USB_HUB_CAPABILITIES_EX)</code>.


### -output-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a user-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff539329">USB_HUB_CAPABILITIES_EX</a> structure. On output, this structure describes the hub capabilities. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the data that is returned at <b>SystemBuffer</b>, or <code>sizeof(USB_HUB_CAPABILITIES_EX)</code>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES. If the hub has not been started or is not functional, the request returns STATUS_UNSUCCESSFUL.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539329">USB_HUB_CAPABILITIES_EX</a>
 

 

