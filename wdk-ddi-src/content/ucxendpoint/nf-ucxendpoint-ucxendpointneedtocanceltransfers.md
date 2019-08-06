---
UID: NF:ucxendpoint.UcxEndpointNeedToCancelTransfers
title: UcxEndpointNeedToCancelTransfers function (ucxendpoint.h)
description: The client driver calls this method before it cancels transfers on the wire.
old-location: buses\_ucxendpointneedtocanceltransfers.htm
tech.root: usbref
ms.assetid: 4DA3FB63-D2D3-43E1-9420-29303176B837
ms.date: 05/07/2018
ms.keywords: UcxEndpointNeedToCancelTransfers, UcxEndpointNeedToCancelTransfers method [Buses], buses._ucxendpointneedtocanceltransfers, ucxendpoint/UcxEndpointNeedToCancelTransfers
ms.topic: function
f1_keywords:
 - "ucxendpoint/UcxEndpointNeedToCancelTransfers"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ucxendpoint.h
api_name:
- UcxEndpointNeedToCancelTransfers
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxEndpointNeedToCancelTransfers function


## -description


The client driver calls this method before it cancels transfers on the wire.


## -parameters




### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.


## -returns



This method does not return a value.




## -remarks



 If needed, UCX coordinates with the hub driver to send a Clear TT buffer command to the TT Hub.

    After that operation completes, UCX invokes the client driver's  EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 

 

