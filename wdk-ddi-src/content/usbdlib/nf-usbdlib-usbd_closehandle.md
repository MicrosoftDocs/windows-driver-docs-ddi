---
UID: NF:usbdlib.USBD_CloseHandle
title: USBD_CloseHandle function (usbdlib.h)
description: The USBD_CloseHandle routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.
old-location: buses\usbd_unregister.htm
tech.root: usbref
ms.assetid: 6876E96D-E249-4B7C-A496-27E3F4A7F7E2
ms.date: 06/24/2019
keywords: ["USBD_CloseHandle function"]
ms.keywords: USBD_CloseHandle, USBD_CloseHandle routine [Buses], buses.usbd_unregister, usbdlib/USBD_CloseHandle
f1_keywords:
 - "usbdlib/USBD_CloseHandle"
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires DDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbdex.lib
- Usbdex.dll
api_name:
- USBD_CloseHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_CloseHandle function


## -description


The  <b>USBD_CloseHandle</b> routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.


## -parameters




### -param USBDHandle [in]

USBD handle to be closed. The handle is retrieved by the client driver in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a> routine.


## -remarks



A client driver should call <b>USBD_CloseHandle</b> in the driver's routine that handles the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> IRP. The client driver must call the routine before sending the IRP down the USB driver stack. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/how-to-add-xrb-support-for-client-drivers">Allocating and Building URBs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a>
 

 

