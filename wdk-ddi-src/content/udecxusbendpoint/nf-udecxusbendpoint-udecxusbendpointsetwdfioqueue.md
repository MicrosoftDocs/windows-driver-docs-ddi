---
UID: NF:udecxusbendpoint.UdecxUsbEndpointSetWdfIoQueue
title: UdecxUsbEndpointSetWdfIoQueue function
author: windows-driver-content
description: Sets a framework queue object with a UDE endpoint.
old-location: buses\udecxusbendpointsetwdfioqueue.htm
old-project: UsbRef
ms.assetid: 48744342-9137-48F5-9071-528974DE6AD5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: udecxusbendpoint/UdecxUsbEndpointSetWdfIoQueue, UdecxUsbEndpointSetWdfIoQueue function [Buses], buses.udecxusbendpointsetwdfioqueue, UdecxUsbEndpointSetWdfIoQueue
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
-	UdecxUsbEndpointSetWdfIoQueue
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# UdecxUsbEndpointSetWdfIoQueue function


## -description


Sets a framework queue object with a UDE endpoint.


## -syntax


````
FORCEINLINE void UdecxUsbEndpointSetWdfIoQueue(
  _In_ UDECXUSBENDPOINT UdecxUsbEndpoint,
  _In_ WDFQUEUE         WdfQueue
);
````


## -parameters




### -param UdecxUsbEndpoint [in]

A handle to a UDE endpoint object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>.


### -param WdfQueue [in]

A handle to a framework queue object that will handle requests sent to the endpoint. The client driver retrieved this pointer in the previous call to <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>. 


## -returns



This function does not return a value.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UdecxUsbEndpointSetWdfIoQueue function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

