---
UID: NF:udecxusbendpoint.UdecxUsbEndpointInitFree
title: UdecxUsbEndpointInitFree function
author: windows-driver-content
description: Release the resources that were allocated by the UdecxUsbSimpleEndpointInitAllocate call.
old-location: buses\udecxusbendpointinitfree.htm
old-project: usbref
ms.assetid: F95BDA95-4667-4EC3-9FE5-C78B453AC0B3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbEndpointInitFree, UdecxUsbEndpointInitFree function [Buses], buses.udecxusbendpointinitfree, udecxusbendpoint/UdecxUsbEndpointInitFree
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
-	UdecxUsbEndpointInitFree
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# UdecxUsbEndpointInitFree function


## -description


Release the resources that were allocated by the  <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate.md">UdecxUsbSimpleEndpointInitAllocate</a> call.


## -syntax


````
FORCEINLINE void UdecxUsbEndpointInitFree(
  _In_ PUDECXUSBENDPOINT_INIT Init
);
````


## -parameters




### -param Init [in]

A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbsimpleendpointinitallocate.md">UdecxUsbSimpleEndpointInitAllocate</a>.


## -returns



This function does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbEndpointInitFree function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

