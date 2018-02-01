---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
title: IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
author: windows-driver-content
description: The class driver sends this request to register a USB string descriptor.
old-location: buses\ioctl_internal_usbfn_register_usb_string.htm
old-project: usbref
ms.assetid: 80CB670A-4E64-4E53-815C-12580BE982B5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_internal_usbfn_register_usb_string, IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING control code [Buses], IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING, usbfnioctl/IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: 
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
-	usbfnioctl.h
apiname:
-	IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The class driver sends this request to register a USB string descriptor.


## -ioctlparameters




### -input-buffer

A pointer to a buffer that contains a  <a href="..\usbfnbase\ns-usbfnbase-_usbfn_usb_string.md">USBFN_USB_STRING</a> structure with the USB string descriptor. 


### -input-buffer-length

The length of the input buffer must be at least <code>sizeof(USBFN_USB_STRING)</code>.


### -output-buffer

NULL.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks


This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.



## -see-also

<a href="..\usbfnbase\ns-usbfnbase-_usbfn_usb_string.md">USBFN_USB_STRING</a>

<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

