---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
title: IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE (usbioctl.h)
description: The IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE I/O request unregisters the driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration.
old-location: buses\ioctl_internal_usb_unregister_composite_driver.htm
tech.root: usbref
ms.assetid: B9DD8FDB-CD78-41BD-BE43-A0F61695B3EB
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE, IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE control, IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE control code [Buses], buses.ioctl_internal_usb_unregister_composite_driver, usbioctl/IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE"
 - "IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> 
   I/O request unregisters the  driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration. The request is successful only if the composite driver was previously registered with the underlying USB driver stack through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_register_composite_device">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> request.



<b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> is a kernel-mode I/O control request. This request targets the Universal Serial Bus (USB) hub physical device object (PDO). This request must be sent at an interrupt request level (IRQL) of PASSIVE_LEVEL.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB driver stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -remarks



You must send the <b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> request in the composite driver's  remove-device (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a>) routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Register a Composite Device</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_register_composite_device">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>
 

 

