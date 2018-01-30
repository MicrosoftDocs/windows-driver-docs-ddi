---
UID: NS:usbbusif._USB_BUS_INFORMATION_LEVEL_0
title: "_USB_BUS_INFORMATION_LEVEL_0"
author: windows-driver-content
description: The USB_BUS_INFORMATION_LEVEL_0 structure is used in conjunction with the QueryBusInformation interface routine to report information about the bus.
old-location: buses\usb_bus_information_level_0.htm
old-project: usbref
ms.assetid: b590493d-59a0-460d-b025-8fac63e62f6a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PUSB_BUS_INFORMATION_LEVEL_0, usbbusif/PUSB_BUS_INFORMATION_LEVEL_0, USB_BUS_INFORMATION_LEVEL_0 structure [Buses], PUSB_BUS_INFORMATION_LEVEL_0 structure pointer [Buses], _USB_BUS_INFORMATION_LEVEL_0, PUSB_BUS_INFORMATION_LEVEL_0, usbbusif/USB_BUS_INFORMATION_LEVEL_0, buses.usb_bus_information_level_0, USB_BUS_INFORMATION_LEVEL_0, usbstrct_19a2e4ab-663a-4cb9-b21c-182d1de11b68.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems.
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
-	usbbusif.h
apiname:
-	USB_BUS_INFORMATION_LEVEL_0
product: Windows
targetos: Windows
req.typenames: USB_BUS_INFORMATION_LEVEL_0, *PUSB_BUS_INFORMATION_LEVEL_0
req.product: Windows 10 or later.
---

# _USB_BUS_INFORMATION_LEVEL_0 structure


## -description


The <b>USB_BUS_INFORMATION_LEVEL_0</b> structure is used in conjunction with the <a href="https://msdn.microsoft.com/cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c">QueryBusInformation</a> interface routine to report information about the bus. 


## -syntax


````
typedef struct _USB_BUS_INFORMATION_LEVEL_0 {
  ULONG TotalBandwidth;
  ULONG ConsumedBandwidth;
} USB_BUS_INFORMATION_LEVEL_0, *PUSB_BUS_INFORMATION_LEVEL_0;
````


## -struct-fields




### -field TotalBandwidth

Specifies the total bandwidth, in bits per second, available on the bus. 


### -field ConsumedBandwidth

Specifies the mean bandwidth that is already in use, in bits per second. 


## -remarks


Caller must set the <i>Level</i> parameter of the <a href="https://msdn.microsoft.com/cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c">QueryBusInformation</a> routine to zero. 

For more information about how to obtain the proper level of USB interface, see <a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">USB Routines</a>.



## -see-also

<a href="https://msdn.microsoft.com/cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c">QueryBusInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUS_INFORMATION_LEVEL_0 structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

