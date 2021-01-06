---
UID: NF:ucxendpoint.UcxEndpointNoPingResponseError
title: UcxEndpointNoPingResponseError function (ucxendpoint.h)
description: Notifies UCX about a &#0034;No Ping Response&#0034; error for a transfer on the specified endpoint object.
old-location: buses\_ucxendpointnopingresponseerror.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxEndpointNoPingResponseError function"]
ms.keywords: UcxEndpointNoPingResponseError, UcxEndpointNoPingResponseError method [Buses], buses._ucxendpointnopingresponseerror, ucxendpoint/UcxEndpointNoPingResponseError
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
 - UcxEndpointNoPingResponseError
 - ucxendpoint/UcxEndpointNoPingResponseError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxendpoint.h
api_name:
 - UcxEndpointNoPingResponseError
---

# UcxEndpointNoPingResponseError function


## -description

Notifies UCX about a "No Ping Response" error for a transfer on
    the specified endpoint object

## -parameters

### -param Endpoint 

[in]
A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
