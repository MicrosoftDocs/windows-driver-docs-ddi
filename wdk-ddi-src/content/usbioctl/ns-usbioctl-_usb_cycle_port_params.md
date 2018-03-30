---
UID: NS:usbioctl._USB_CYCLE_PORT_PARAMS
title: "_USB_CYCLE_PORT_PARAMS"
author: windows-driver-content
description: The USB_CYCLE_PORT_PARAMS structure is used with the IOCTL_USB_HUB_CYCLE_PORT I/O control request to power cycle the port that is associated with the PDO that receives the request.
old-location: buses\usb_cycle_port_params.htm
old-project: usbref
ms.assetid: 357C62F3-43FE-4132-9233-7BFAD2CE95C5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_CYCLE_PORT_PARAMS, PUSB_CYCLE_PORT_PARAMS, PUSB_CYCLE_PORT_PARAMS structure pointer [Buses], USB_CYCLE_PORT_PARAMS, USB_CYCLE_PORT_PARAMS structure [Buses], _USB_CYCLE_PORT_PARAMS, buses.usb_cycle_port_params, usbioctl/PUSB_CYCLE_PORT_PARAMS, usbioctl/USB_CYCLE_PORT_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: TBD
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_CYCLE_PORT_PARAMS
product: Windows
targetos: Windows
req.typenames: USB_CYCLE_PORT_PARAMS, *PUSB_CYCLE_PORT_PARAMS
req.product: Windows 10 or later.
---

# _USB_CYCLE_PORT_PARAMS structure


## -description


The <b>USB_CYCLE_PORT_PARAMS</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537340">IOCTL_USB_HUB_CYCLE_PORT</a> I/O control request to power cycle the port that is associated with the PDO that receives the request.<div class="alert"><b>Note</b>  <a href="https://msdn.microsoft.com/library/windows/hardware/ff537340">IOCTL_USB_HUB_CYCLE_PORT</a> has been deprecated in Windows Vista and later operating systems. Do not use. 
</div>
<div> </div>



## -struct-fields




### -field ConnectionIndex

Specifies the port number starting at 1.


### -field StatusReturned

On return, contains the USBD status of the operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537340">IOCTL_USB_HUB_CYCLE_PORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
 

 

