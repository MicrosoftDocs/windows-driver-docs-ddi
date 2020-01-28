---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
title: IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS (usbioctl.h)
description: The IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS I/O request returns information about the host controller the USB device is attached to, and the device's location in the USB device tree.
old-location: buses\ioctl_internal_usb_get_topology_address.htm
tech.root: usbref
ms.assetid: 15a196de-7d6a-408a-97e1-58d6756433db
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS, IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS control, IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS control code [Buses], buses.ioctl_internal_usb_get_topology_address, usbioctl/IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS IOCTL


## -description


The <b>IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS</b> 
   I/O request returns information about the host controller the USB device is attached to, and the device's location in the USB device tree.

<b>IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of DISPATCH_LEVEL or lower.


## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_topology_address">USB_TOPOLOGY_ADDRESS</a> structure to receive the device topology information.


### -input-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_topology_address">USB_TOPOLOGY_ADDRESS</a> structure.


### -output-buffer

<b>Parameters.Others.Argument1</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_topology_address">USB_TOPOLOGY_ADDRESS</a> structure containing the device topology information.


### -output-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_topology_address">USB_TOPOLOGY_ADDRESS</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The hub or port driver sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -see-also




<b>USB_TOPOLOGY_ADDRESS</b>
 

 

