---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_CAPABILITIES
title: IOCTL_USB_GET_HUB_CAPABILITIES (usbioctl.h)
description: The IOCTL_USB_GET_HUB_CAPABILITIES I/O control request retrieves the capabilities of a USB hub.
old-location: buses\ioctl_usb_get_hub_capabilities.htm
tech.root: usbref
ms.assetid: 2275b197-6298-470f-bb96-91088d763160
ms.date: 05/07/2018
keywords: ["IOCTL_USB_GET_HUB_CAPABILITIES IOCTL"]
ms.keywords: IOCTL_USB_GET_HUB_CAPABILITIES, IOCTL_USB_GET_HUB_CAPABILITIES control, IOCTL_USB_GET_HUB_CAPABILITIES control code [Buses], buses.ioctl_usb_get_hub_capabilities, usbioctl/IOCTL_USB_GET_HUB_CAPABILITIES, usbirp_0db4e801-763f-4d2f-aedf-2e3798fb191c.xml
f1_keywords:
 - "usbioctl/IOCTL_USB_GET_HUB_CAPABILITIES"
 - "IOCTL_USB_GET_HUB_CAPABILITIES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_USB_GET_HUB_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_HUB_CAPABILITIES IOCTL


## -description



The <b>IOCTL_USB_GET_HUB_CAPABILITIES</b> I/O control request retrieves the capabilities of a USB hub. <b>Note</b>  This request is replaced by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_capabilities_ex">IOCTL_USB_GET_HUB_CAPABILITIES_EX</a> in Windows Vista.



<b>IOCTL_USB_GET_HUB_CAPABILITIES</b>  is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities">USB_HUB_CAPABILITIES</a> structure that describes the hub capabilities. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer in <b>SystemBuffer</b>. The output buffer size must be <code>>= sizeof(USB_HUB_CAPABILITIES)</code>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_capabilities_ex">IOCTL_USB_GET_HUB_CAPABILITIES_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_capabilities">USB_HUB_CAPABILITIES</a>
 

 

