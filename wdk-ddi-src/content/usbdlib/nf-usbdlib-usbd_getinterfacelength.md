---
UID: NF:usbdlib.USBD_GetInterfaceLength
title: USBD_GetInterfaceLength function (usbdlib.h)
description: The USBD_GetInterfaceLength routine obtains the length of a given interface descriptor, including the length of all endpoint descriptors contained within the interface.
old-location: buses\usbd_getinterfacelength.htm
tech.root: usbref
ms.assetid: bcfc2b11-d89c-40f8-95ce-07a599e2a2bb
ms.date: 05/07/2018
ms.keywords: USBD_GetInterfaceLength, USBD_GetInterfaceLength routine [Buses], buses.usbd_getinterfacelength, usbdlib/USBD_GetInterfaceLength, usbfunc_d462af93-f7ec-429f-9719-4b09af55236c.xml
f1_keywords:
 - "usbdlib/USBD_GetInterfaceLength"
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
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
req.lib: Usbd.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbd.lib
- Usbd.dll
api_name:
- USBD_GetInterfaceLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_GetInterfaceLength function


## -description



   The <b>USBD_GetInterfaceLength</b> routine obtains the length of a given interface descriptor, including the length of all endpoint descriptors contained within the interface.


## -parameters




### -param InterfaceDescriptor [in]

Pointer to a interface descriptor for which to obtain the length.


### -param BufferEnd [in]

Pointer to the position within a buffer at which to stop searching for the length of the interface and associated endpoints.


## -returns



<b>USBD_GetInterfaceLength</b> returns the length, in bytes, of the interface descriptor and all associated endpoint descriptors contained within the interface.




## -remarks



Callers can use this routine to obtain the length of an interface and associated endpoints that are contained within another buffer. For example, a caller could specify a location inside of a larger buffer for <i>InterfaceDescriptor</i> and the beginning of a location of another interface descriptor for <i>BufferEnd</i>. This will cause the routine to search only from the beginning of the interface descriptor specified by <i>InterfaceDescriptor</i> until either it finds another interface descriptor or it reaches the position specified by <i>BufferEnd</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>
 

 

