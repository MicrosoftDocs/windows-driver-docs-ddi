---
UID: NF:ufxclient.UfxEndpointGetTransferQueue
title: UfxEndpointGetTransferQueue function
description: Returns the transfer queue previously created by UfxEndpointCreate.
old-location: buses\ufxendpointgettransferqueue.htm
tech.root: usbref
ms.assetid: 74E78EC9-4D2B-4CA4-AC00-03EB7433617C
ms.date: 05/07/2018
ms.keywords: UfxEndpointGetTransferQueue, UfxEndpointGetTransferQueue method [Buses], buses.ufxendpointgettransferqueue, ufxclient/UfxEndpointGetTransferQueue
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxEndpointGetTransferQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxEndpointGetTransferQueue function


## -description


Returns the transfer queue previously created by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.


## -parameters




### -param UfxEndpoint [in]

A handle to an endpoint object returned from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.


## -returns



A handle to a framework queue object.




## -remarks



For an code example that shows how to create an endpoint object and initialize its context, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>
 

 

