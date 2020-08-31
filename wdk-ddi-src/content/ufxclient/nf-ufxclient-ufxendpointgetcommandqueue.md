---
UID: NF:ufxclient.UfxEndpointGetCommandQueue
title: UfxEndpointGetCommandQueue function (ufxclient.h)
description: Returns the command queue previously created by UfxEndpointCreate.
old-location: buses\ufxendpointgetcommandqueue.htm
tech.root: usbref
ms.assetid: BF84F0E4-3B0D-45B8-AC06-F6F761A37234
ms.date: 05/07/2018
keywords: ["UfxEndpointGetCommandQueue function"]
ms.keywords: UfxEndpointGetCommandQueue, UfxEndpointGetCommandQueue method [Buses], buses.ufxendpointgetcommandqueue, ufxclient/UfxEndpointGetCommandQueue
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UfxEndpointGetCommandQueue
 - ufxclient/UfxEndpointGetCommandQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxEndpointGetCommandQueue
---

# UfxEndpointGetCommandQueue function


## -description

Returns the command queue previously created by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

## -parameters

### -param UfxEndpoint 

[in]
A handle to an endpoint object returned from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

## -returns

A handle to a framework queue object.

## -remarks

For an code example that shows how to create an endpoint object and initialize its context, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>

