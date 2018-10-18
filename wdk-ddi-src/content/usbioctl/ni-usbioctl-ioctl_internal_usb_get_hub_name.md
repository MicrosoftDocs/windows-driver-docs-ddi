---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_HUB_NAME
title: IOCTL_INTERNAL_USB_GET_HUB_NAME
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_HUB_NAME I/O request is used by drivers to retrieve the UNICODE symbolic name for the target PDO if the PDO is for a hub.
old-location: buses\ioctl_internal_usb_get_hub_name.htm
tech.root: usbref
ms.assetid: af0a1cfe-16e8-4356-9b5c-2e2523869906
ms.date: 5/7/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_HUB_NAME, IOCTL_INTERNAL_USB_GET_HUB_NAME control, IOCTL_INTERNAL_USB_GET_HUB_NAME control code [Buses], buses.ioctl_internal_usb_get_hub_name, usbioctl/IOCTL_INTERNAL_USB_GET_HUB_NAME, usbirp_54327688-c86b-4d05-b81d-5368f694f9ca.xml
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
-	Usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_GET_HUB_NAME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_HUB_NAME IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_GET_HUB_NAME</b> I/O request is used by drivers to retrieve the UNICODE symbolic name for the target PDO if the PDO is for a hub. Otherwise a <b>NULL</b> string is returned. 

Drivers can use the symbolic name to retrieve additional information about the hub through user-mode I/O control requests and WMI calls.

<b>IOCTL_INTERNAL_USB_GET_HUB_NAME</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.




## -ioctlparameters




### -input-buffer

<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540025">USB_HUB_NAME</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> is the length of the buffer (in bytes) passed in the <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> field.


### -output-buffer

<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is filled with the root hub's symbolic name.


### -output-buffer-length

The length of the root hub's symbolic name.


### -in-out-buffer








### -inout-buffer-length








### -status-block

A lower-level driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status. It will set <b>Irp-&gt;IoStatus.Information</b> to the number of bytes required to hold the USB_ROOT_HUB_NAME structure. If the request fails, the driver can use this information to resubmit the request with a big enough buffer.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540142">USB_ROOT_HUB_NAME</a>
 

 

