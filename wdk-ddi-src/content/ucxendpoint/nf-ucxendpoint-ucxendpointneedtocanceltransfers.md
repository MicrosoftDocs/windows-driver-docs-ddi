---
UID: NF:ucxendpoint.UcxEndpointNeedToCancelTransfers
title: UcxEndpointNeedToCancelTransfers function (ucxendpoint.h)
description: The client driver calls this method before it cancels transfers on the wire.
old-location: buses\_ucxendpointneedtocanceltransfers.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxEndpointNeedToCancelTransfers function"]
ms.keywords: UcxEndpointNeedToCancelTransfers, UcxEndpointNeedToCancelTransfers method [Buses], buses._ucxendpointneedtocanceltransfers, ucxendpoint/UcxEndpointNeedToCancelTransfers
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxEndpointNeedToCancelTransfers
 - ucxendpoint/UcxEndpointNeedToCancelTransfers
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxendpoint.h
api_name:
 - UcxEndpointNeedToCancelTransfers
---

# UcxEndpointNeedToCancelTransfers function


## -description

The client driver calls this method before it cancels transfers on the wire.

## -parameters

### -param Endpoint 

[in]
A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.

## -remarks

If needed, UCX coordinates with the hub driver to send a Clear TT buffer command to the TT Hub.

After that operation completes, UCX invokes the client driver's  EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
