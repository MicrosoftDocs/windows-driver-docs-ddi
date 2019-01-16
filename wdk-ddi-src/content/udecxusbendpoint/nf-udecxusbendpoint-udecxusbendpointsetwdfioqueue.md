---
UID: NF:udecxusbendpoint.UdecxUsbEndpointSetWdfIoQueue
title: UdecxUsbEndpointSetWdfIoQueue function
description: Sets a framework queue object with a UDE endpoint.
old-location: buses\udecxusbendpointsetwdfioqueue.htm
tech.root: usbref
ms.assetid: 48744342-9137-48F5-9071-528974DE6AD5
ms.date: 05/07/2018
ms.keywords: UdecxUsbEndpointSetWdfIoQueue, UdecxUsbEndpointSetWdfIoQueue function [Buses], buses.udecxusbendpointsetwdfioqueue, udecxusbendpoint/UdecxUsbEndpointSetWdfIoQueue
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbEndpointSetWdfIoQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbEndpointSetWdfIoQueue function


## -description


Sets a framework queue object with a UDE endpoint.


## -parameters




### -param UdecxUsbEndpoint [in]

A handle to a UDE endpoint object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627983">UdecxUsbEndpointCreate</a>.


### -param WdfQueue [in]

A handle to a framework queue object that will handle requests sent to the endpoint. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>. 


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

