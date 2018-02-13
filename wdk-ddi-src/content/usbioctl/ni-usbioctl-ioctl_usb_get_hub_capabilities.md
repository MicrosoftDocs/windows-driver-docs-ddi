---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_CAPABILITIES
title: IOCTL_USB_GET_HUB_CAPABILITIES
author: windows-driver-content
description: The IOCTL_USB_GET_HUB_CAPABILITIES I/O control request retrieves the capabilities of a USB hub.
old-location: buses\ioctl_usb_get_hub_capabilities.htm
old-project: usbref
ms.assetid: 2275b197-6298-470f-bb96-91088d763160
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_usb_get_hub_capabilities, IOCTL_USB_GET_HUB_CAPABILITIES control code [Buses], IOCTL_USB_GET_HUB_CAPABILITIES, usbioctl/IOCTL_USB_GET_HUB_CAPABILITIES, usbirp_0db4e801-763f-4d2f-aedf-2e3798fb191c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_GET_HUB_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_HUB_CAPABILITIES IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_USB_GET_HUB_CAPABILITIES</b> I/O control request retrieves the capabilities of a USB hub. <b>Note</b>  This request is replaced by <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_capabilities_ex.md">IOCTL_USB_GET_HUB_CAPABILITIES_EX</a> in Windows Vista.



<b>IOCTL_USB_GET_HUB_CAPABILITIES</b>  is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated <a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities.md">USB_HUB_CAPABILITIES</a> structure that describes the hub capabilities. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer in <b>SystemBuffer</b>. The output buffer size must be <code>&gt;= sizeof(USB_HUB_CAPABILITIES)</code>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_capabilities_ex.md">IOCTL_USB_GET_HUB_CAPABILITIES_EX</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities.md">USB_HUB_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_HUB_CAPABILITIES control code%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

