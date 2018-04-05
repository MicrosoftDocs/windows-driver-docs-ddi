---
UID: NS:usbioctl._USB_HUB_CAPABILITIES_EX
title: "_USB_HUB_CAPABILITIES_EX"
author: windows-driver-content
description: The USB_HUB_CAPABILITIES_EX structure is used with the IOCTL_USB_GET_HUB_CAPABILITIES I/O control request to retrieve the capabilities of a particular USB hub.
old-location: buses\usb_hub_capabilities_ex.htm
old-project: usbref
ms.assetid: deb8d710-6137-4f69-8fde-00d46cdb6f4f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_HUB_CAPABILITIES_EX, PUSB_HUB_CAPABILITIES_EX, PUSB_HUB_CAPABILITIES_EX structure pointer [Buses], USB_HUB_CAPABILITIES_EX, USB_HUB_CAPABILITIES_EX structure [Buses], _USB_HUB_CAPABILITIES_EX, buses.usb_hub_capabilities_ex, usbioctl/PUSB_HUB_CAPABILITIES_EX, usbioctl/USB_HUB_CAPABILITIES_EX, usbstrct_42446556-393a-4d58-934e-f63d62fa3c07.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_HUB_CAPABILITIES_EX
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_CAPABILITIES_EX, *PUSB_HUB_CAPABILITIES_EX
req.product: Windows 10 or later.
---

# _USB_HUB_CAPABILITIES_EX structure


## -description


The <b>USB_HUB_CAPABILITIES_EX</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537312">IOCTL_USB_GET_HUB_CAPABILITIES</a> I/O control request to retrieve the capabilities of a particular USB hub.


## -struct-fields




### -field CapabilityFlags

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff539330">USB_HUB_CAP_FLAGS</a> structure that reports the hub capabilities.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537312">IOCTL_USB_GET_HUB_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539330">USB_HUB_CAP_FLAGS</a>
 

 

