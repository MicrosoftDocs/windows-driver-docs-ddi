---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
title: IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS I/O request returns information about the host controller the USB device is attached to, and the device's location in the USB device tree.
old-location: buses\ioctl_internal_usb_get_topology_address.htm
old-project: usbref
ms.assetid: 15a196de-7d6a-408a-97e1-58d6756433db
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_internal_usb_get_topology_address, IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS control code [Buses], IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS, usbioctl/IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS</b> 
   I/O request returns information about the host controller the USB device is attached to, and the device's location in the USB device tree.

<b>IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of DISPATCH_LEVEL or lower.


## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> points to a <a href="..\usbioctl\ns-usbioctl-_usb_topology_address.md">USB_TOPOLOGY_ADDRESS</a> structure to receive the device topology information.


### -input-buffer-length

The size of a <a href="..\usbioctl\ns-usbioctl-_usb_topology_address.md">USB_TOPOLOGY_ADDRESS</a> structure.


### -output-buffer

<b>Parameters.Others.Argument1</b> points to a <a href="..\usbioctl\ns-usbioctl-_usb_topology_address.md">USB_TOPOLOGY_ADDRESS</a> structure containing the device topology information.


### -output-buffer-length

The size of a <a href="..\usbioctl\ns-usbioctl-_usb_topology_address.md">USB_TOPOLOGY_ADDRESS</a> structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The hub or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -see-also

<b>USB_TOPOLOGY_ADDRESS</b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

