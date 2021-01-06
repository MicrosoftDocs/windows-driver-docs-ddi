---
UID: NF:ufxclient.UfxEndpointGetTransferQueue
title: UfxEndpointGetTransferQueue function (ufxclient.h)
description: Returns the transfer queue previously created by UfxEndpointCreate.
old-location: buses\ufxendpointgettransferqueue.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UfxEndpointGetTransferQueue function"]
ms.keywords: UfxEndpointGetTransferQueue, UfxEndpointGetTransferQueue method [Buses], buses.ufxendpointgettransferqueue, ufxclient/UfxEndpointGetTransferQueue
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
 - UfxEndpointGetTransferQueue
 - ufxclient/UfxEndpointGetTransferQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxEndpointGetTransferQueue
---

# UfxEndpointGetTransferQueue function


## -description

Returns the transfer queue previously created by <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

## -parameters

### -param UfxEndpoint 

[in]
A handle to an endpoint object returned from a previous call to <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

## -returns

A handle to a framework queue object.

## -remarks

For an code example that shows how to create an endpoint object and initialize its context, see the Remarks section of <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>
