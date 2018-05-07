---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX
title: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX
author: windows-driver-content
description: The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request retrieves information about a USB port and the device that is attached to the port, if there is one.Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.
old-location: buses\ioctl_usb_get_node_connection_information_ex.htm
old-project: usbref
ms.assetid: d056dd82-815d-42da-8d2a-490474f68782
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX control, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX control code [Buses], buses.ioctl_usb_get_node_connection_information_ex, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX, usbirp_61c188b5-2820-4601-b2de-08bf30109824.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP, Windows Server 2003, and later.
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
-	IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX IOCTL


## -description



The <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</b> request retrieves information about a USB port and the device that is attached to the port, if there is one.

Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.

<b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure. On input, the <b>ConnectionIndex</b> member of this structure must contain a number greater than or equal to 1 that indicates the number of the port whose connection information is to be reported. The hub driver returns connection information in the remaining members of <b>USB_NODE_CONNECTION_INFORMATION_EX</b>.


### -input-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure.


### -output-buffer

The USB hub driver will return information about the indicated connection in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure that is pointed to by <b>AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a>
 

 

