---
UID: NF:usbdlib.USBD_GetInterfaceLength
title: USBD_GetInterfaceLength function
author: windows-driver-content
description: The USBD_GetInterfaceLength routine obtains the length of a given interface descriptor, including the length of all endpoint descriptors contained within the interface.
old-location: buses\usbd_getinterfacelength.htm
old-project: usbref
ms.assetid: bcfc2b11-d89c-40f8-95ce-07a599e2a2bb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_GetInterfaceLength
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_GetInterfaceLength
req.alt-loc: Usbd.lib,Usbd.dll
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
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_GetInterfaceLength function



## -description

   The <b>USBD_GetInterfaceLength</b> routine obtains the length of a given interface descriptor, including the length of all endpoint descriptors contained within the interface.



## -syntax

````
__declspec USBD_GetInterfaceLength(
  _In_ PUSB_INTERFACE_DESCRIPTOR InterfaceDescriptor,
  _In_ PUCHAR                    BufferEnd
);
````


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
<dl>
<dt><a href="usb_reference.htm#client">USB device driver programming reference</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_GetInterfaceLength routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

