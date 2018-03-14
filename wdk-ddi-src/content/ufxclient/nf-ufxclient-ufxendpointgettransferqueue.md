---
UID: NF:ufxclient.UfxEndpointGetTransferQueue
title: UfxEndpointGetTransferQueue function
author: windows-driver-content
description: Returns the transfer queue previously created by UfxEndpointCreate.
old-location: buses\ufxendpointgettransferqueue.htm
old-project: usbref
ms.assetid: 74E78EC9-4D2B-4CA4-AC00-03EB7433617C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxEndpointGetTransferQueue, UfxEndpointGetTransferQueue method [Buses], buses.ufxendpointgettransferqueue, ufxclient/UfxEndpointGetTransferQueue
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: 
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
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxEndpointGetTransferQueue function


## -description


Returns the transfer queue previously created by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.


## -syntax


````
WDFQUEUE UfxEndpointGetTransferQueue(
  [in] UFXENDPOINT UfxEndpoint
);
````


## -parameters




### -param UfxEndpoint [in]

A handle to an endpoint object returned from a previous call to <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.


## -returns



A handle to a framework queue object.




## -remarks



For an code example that shows how to create an endpoint object and initialize its context, see the Remarks section of <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.




## -see-also

<a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>



 

 


