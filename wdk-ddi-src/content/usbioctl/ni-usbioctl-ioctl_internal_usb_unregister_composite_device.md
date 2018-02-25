---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
title: IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE I/O request unregisters the driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration.
old-location: buses\ioctl_internal_usb_unregister_composite_driver.htm
old-project: UsbRef
ms.assetid: B9DD8FDB-CD78-41BD-BE43-A0F61695B3EB
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE, IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE control code [Buses], buses.ioctl_internal_usb_unregister_composite_driver, usbioctl/IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The <b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> 
   I/O request unregisters the  driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration. The request is successful only if the composite driver was previously registered with the underlying USB driver stack through the <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a> request.



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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB driver stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -remarks



You must send the <b>IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</b> request in the composite driver's  remove-device (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>) routine.




## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_register_composite_device.md">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

