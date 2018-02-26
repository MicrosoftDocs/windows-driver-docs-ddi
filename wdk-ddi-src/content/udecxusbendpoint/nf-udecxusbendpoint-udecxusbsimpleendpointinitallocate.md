---
UID: NF:udecxusbendpoint.UdecxUsbSimpleEndpointInitAllocate
title: UdecxUsbSimpleEndpointInitAllocate function
author: windows-driver-content
description: Allocates memory for an initialization structure that is used to create a simple endpoint for the specified virtual USB device.
old-location: buses\udecxusbsimpleendpointinitallocate.htm
old-project: usbref
ms.assetid: 1BF79756-F55D-4F13-A03C-35F7880C5B21
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, E, I, S, U, UdecxUsbSimpleEndpointInitAllocate, UdecxUsbSimpleEndpointInitAllocate function [Buses], a, b, buses.udecxusbsimpleendpointinitallocate, c, d, e, i, l, m, n, o, p, s, t, udecxusbendpoint/UdecxUsbSimpleEndpointInitAllocate, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxusbendpoint.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUsbSimpleEndpointInitAllocate
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# UdecxUsbSimpleEndpointInitAllocate function


## -description


Allocates memory for an initialization  structure that is used to create a simple endpoint for the specified virtual USB device.  


## -syntax


````
PUDECXUSBENDPOINT_INIT UdecxUsbSimpleEndpointInitAllocate(
  _In_ UDECXUSBDEVICE UdecxUsbDevice
);
````


## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


## -returns



This method returns a pointer to an opaque <b>UDECXUSBENDPOINT_INIT</b> structure that contains the initialization parameters. The structure is allocated by the USB device emulation  class extension (UdeCx).




## -remarks



The UDE client driver calls this method to allocate parameters for a simple endpoint that is created by a subsequent call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>. If the device is not created or the driver is finished using the resources, the driver must free the resources by calling <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointinitfree.md">UdecxUsbEndpointInitFree</a>.

The only valid time to create simple endpoints is after creating a the UDE device object and before calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceplugin.md">UdecxUsbDevicePlugIn</a> on the device.





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbSimpleEndpointInitAllocate function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

