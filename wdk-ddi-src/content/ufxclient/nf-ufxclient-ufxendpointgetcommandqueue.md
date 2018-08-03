---
UID: NF:ufxclient.UfxEndpointGetCommandQueue
title: UfxEndpointGetCommandQueue function
author: windows-driver-content
description: Returns the command queue previously created by UfxEndpointCreate.
old-location: buses\ufxendpointgetcommandqueue.htm
tech.root: usbref
ms.assetid: BF84F0E4-3B0D-45B8-AC06-F6F761A37234
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UfxEndpointGetCommandQueue, UfxEndpointGetCommandQueue method [Buses], buses.ufxendpointgetcommandqueue, ufxclient/UfxEndpointGetCommandQueue
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
-	UfxEndpointGetCommandQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxEndpointGetCommandQueue function


## -description


Returns the command queue previously created by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.


## -parameters




### -param UfxEndpoint [in]

A handle to an endpoint object returned from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.


## -returns



A handle to a framework queue object.




## -remarks



For an code example that shows how to create an endpoint object and initialize its context, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>
 

 

