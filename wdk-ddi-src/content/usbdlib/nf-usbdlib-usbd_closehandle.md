---
UID: NF:usbdlib.USBD_CloseHandle
title: USBD_CloseHandle function
author: windows-driver-content
description: The USBD_CloseHandle routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.
old-location: buses\usbd_unregister.htm
old-project: usbref
ms.assetid: 6876E96D-E249-4B7C-A496-27E3F4A7F7E2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: USBD_CloseHandle, USBD_CloseHandle routine [Buses], buses.usbd_unregister, usbdlib/USBD_CloseHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	USBD_CloseHandle
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_CloseHandle function


## -description


The  <b>USBD_CloseHandle</b> routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.


## -parameters




### -param USBDHandle [in]

USBD handle to be closed. The handle is retrieved by the client driver in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a> routine.


## -returns



This routine does not return a value.




## -remarks



A client driver should call <b>USBD_CloseHandle</b> in the driver's routine that handles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP. The client driver must call the routine before sending the IRP down the USB driver stack. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a>
 

 

