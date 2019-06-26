---
UID: NF:usbdlib.USBD_UrbFree
title: USBD_UrbFree function (usbdlib.h)
description: The USBD_UrbFree routine releases the URB that is allocated by USBD_UrbAllocate, USBD_IsochUrbAllocate, USBD_SelectConfigUrbAllocateAndBuild, or USBD_SelectInterfaceUrbAllocateAndBuild.
old-location: buses\usbd_urbfree.htm
tech.root: usbref
ms.assetid: DD80BAA0-EC01-4231-827A-962580D1E201
ms.date: 06/24/2019
ms.keywords: USBD_UrbFree, USBD_UrbFree routine [Buses], buses.usbd_urbfree, usbdlib/USBD_UrbFree
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbdex.lib
- Usbdex.dll
api_name:
- USBD_UrbFree
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_UrbFree function


## -description


The <b>USBD_UrbFree</b> routine releases the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> that is allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_isochurballocate">USBD_IsochUrbAllocate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_selectconfigurballocateandbuild">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_selectinterfaceurballocateandbuild">USBD_SelectInterfaceUrbAllocateAndBuild</a>.


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a> routine.


### -param Urb [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure to be released.


## -returns



This routine does not return a value.




## -remarks



You must call <b>USBD_UrbFree</b> to release the URB allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a> after the request is complete. 

Failure to call <b>USBD_UrbFree</b> can cause a memory leak. 

For a code example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/how-to-add-xrb-support-for-client-drivers">Allocating and Building URBs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a>
 

 

