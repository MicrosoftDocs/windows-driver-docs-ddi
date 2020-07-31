---
UID: NS:usbbusif._USB_BUS_INFORMATION_LEVEL_0
title: _USB_BUS_INFORMATION_LEVEL_0 (usbbusif.h)
description: The USB_BUS_INFORMATION_LEVEL_0 structure is used in conjunction with the QueryBusInformation interface routine to report information about the bus.
old-location: buses\usb_bus_information_level_0.htm
tech.root: usbref
ms.assetid: b590493d-59a0-460d-b025-8fac63e62f6a
ms.date: 05/07/2018
keywords: ["_USB_BUS_INFORMATION_LEVEL_0 structure"]
ms.keywords: "*PUSB_BUS_INFORMATION_LEVEL_0, PUSB_BUS_INFORMATION_LEVEL_0, PUSB_BUS_INFORMATION_LEVEL_0 structure pointer [Buses], USB_BUS_INFORMATION_LEVEL_0, USB_BUS_INFORMATION_LEVEL_0 structure [Buses], _USB_BUS_INFORMATION_LEVEL_0, buses.usb_bus_information_level_0, usbbusif/PUSB_BUS_INFORMATION_LEVEL_0, usbbusif/USB_BUS_INFORMATION_LEVEL_0, usbstrct_19a2e4ab-663a-4cb9-b21c-182d1de11b68.xml"
f1_keywords:
 - "usbbusif/USB_BUS_INFORMATION_LEVEL_0"
 - "USB_BUS_INFORMATION_LEVEL_0"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbbusif.h
api_name:
- USB_BUS_INFORMATION_LEVEL_0
targetos: Windows
req.typenames: USB_BUS_INFORMATION_LEVEL_0, *PUSB_BUS_INFORMATION_LEVEL_0
---

# _USB_BUS_INFORMATION_LEVEL_0 structure


## -description


The <b>USB_BUS_INFORMATION_LEVEL_0</b> structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/nc-usbbusif-pusb_busiffn_query_bus_information">QueryBusInformation</a> interface routine to report information about the bus. 


## -struct-fields




### -field TotalBandwidth

Specifies the total bandwidth, in bits per second, available on the bus. 


### -field ConsumedBandwidth

Specifies the mean bandwidth that is already in use, in bits per second. 


## -remarks



Caller must set the <i>Level</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/nc-usbbusif-pusb_busiffn_query_bus_information">QueryBusInformation</a> routine to zero. 

For more information about how to obtain the proper level of USB interface, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540046(v=vs.85)">USB Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/nc-usbbusif-pusb_busiffn_query_bus_information">QueryBusInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>
 

 

