---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_INFORMATION_EX
title: IOCTL_USB_GET_HUB_INFORMATION_EX
author: windows-driver-content
description: The IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request is sent by an application to retrieve information about a USB hub in a USB_HUB_INFORMATION_EX structure.The request retrieves the highest port number on the hub.
old-location: buses\ioctl_usb_get_hub_information_ex.htm
old-project: usbref
ms.assetid: 518AB292-A1E7-48CE-B967-C6559580E326
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_usb_get_hub_information_ex, IOCTL_USB_GET_HUB_INFORMATION_EX control code [Buses], IOCTL_USB_GET_HUB_INFORMATION_EX, usbioctl/IOCTL_USB_GET_HUB_INFORMATION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_GET_HUB_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_HUB_INFORMATION_EX IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_USB_GET_HUB_INFORMATION_EX</b> I/O control request is sent by an application to retrieve information about a USB hub in a <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure.

The request retrieves the highest port number on the hub. For USB 2.0 and SuperSpeed hubs (non-root hubs), the request also retrieves the associated hub descriptors, as defined in USB 2.0 and 3.0 Specifications, respectively. 

<b>IOCTL_USB_GET_HUB_INFORMATION_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a caller-allocated    <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member indicates the size, in bytes, of the caller-allocated buffer whose size equals <code>sizeof(USB_HUB_INFORMATION_EX)</code>.


### -output-buffer

 On output, the <a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a> structure that is pointed to by  <b>AssociatedIrp.SystemBuffer</b> is filled with information about the hub. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer <b>SystemBuffer</b>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB driver stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_HUB_INFORMATION_EX control code%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

