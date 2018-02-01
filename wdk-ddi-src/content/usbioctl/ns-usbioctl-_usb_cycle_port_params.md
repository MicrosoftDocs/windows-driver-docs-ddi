---
UID: NS:usbioctl._USB_CYCLE_PORT_PARAMS
title: "_USB_CYCLE_PORT_PARAMS"
author: windows-driver-content
description: The USB_CYCLE_PORT_PARAMS structure is used with the IOCTL_USB_HUB_CYCLE_PORT I/O control request to power cycle the port that is associated with the PDO that receives the request.
old-location: buses\usb_cycle_port_params.htm
old-project: usbref
ms.assetid: 357C62F3-43FE-4132-9233-7BFAD2CE95C5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PUSB_CYCLE_PORT_PARAMS, _USB_CYCLE_PORT_PARAMS, USB_CYCLE_PORT_PARAMS, usbioctl/USB_CYCLE_PORT_PARAMS, USB_CYCLE_PORT_PARAMS structure [Buses], PUSB_CYCLE_PORT_PARAMS, usbioctl/PUSB_CYCLE_PORT_PARAMS, PUSB_CYCLE_PORT_PARAMS structure pointer [Buses], buses.usb_cycle_port_params"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_CYCLE_PORT_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PUSB_CYCLE_PORT_PARAMS, USB_CYCLE_PORT_PARAMS"
req.product: Windows 10 or later.
---

# _USB_CYCLE_PORT_PARAMS structure


## -description


The <b>USB_CYCLE_PORT_PARAMS</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_hub_cycle_port.md">IOCTL_USB_HUB_CYCLE_PORT</a> I/O control request to power cycle the port that is associated with the PDO that receives the request.<div class="alert"><b>Note</b>  <a href="..\usbioctl\ni-usbioctl-ioctl_usb_hub_cycle_port.md">IOCTL_USB_HUB_CYCLE_PORT</a> has been deprecated in Windows Vista and later operating systems. Do not use. 
</div>
<div> </div>



## -syntax


````
typedef struct _USB_CYCLE_PORT_PARAMS {
  ULONG ConnectionIndex;
  ULONG StatusReturned;
} USB_CYCLE_PORT_PARAMS, *PUSB_CYCLE_PORT_PARAMS;
````


## -struct-fields




### -field ConnectionIndex

Specifies the port number starting at 1.


### -field StatusReturned

On return, contains the USBD status of the operation.


## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_hub_cycle_port.md">IOCTL_USB_HUB_CYCLE_PORT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CYCLE_PORT_PARAMS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

