---
UID: NF:ucxendpoint.UcxEndpointGetStaticStreamsReferenced
title: UcxEndpointGetStaticStreamsReferenced function (ucxendpoint.h)
description: Returns a referenced static streams object for the specified endpoint.
old-location: buses\_ucxendpointgetstaticstreamsreferenced.htm
tech.root: usbref
ms.assetid: A9AB43A9-1409-4AA4-99DE-66D558F2303C
ms.date: 05/07/2018
keywords: ["UcxEndpointGetStaticStreamsReferenced function"]
ms.keywords: UcxEndpointGetStaticStreamsReferenced, UcxEndpointGetStaticStreamsReferenced method [Buses], buses._ucxendpointgetstaticstreamsreferenced, ucxendpoint/UcxEndpointGetStaticStreamsReferenced
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
 - UcxEndpointGetStaticStreamsReferenced
 - ucxendpoint/UcxEndpointGetStaticStreamsReferenced
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxendpoint.h
api_name:
 - UcxEndpointGetStaticStreamsReferenced
---

# UcxEndpointGetStaticStreamsReferenced function


## -description

Returns a referenced static streams object for the specified endpoint.

## -parameters

### -param Endpoint 

[in]
A handle to the endpoint object for which the static streams object is requested. The client driver retrieved the handle in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.

### -param Tag 

[in]
A driver-defined value that the framework stores as an identification tag for the object reference.

## -returns

A handle to the stream object if it is opened with the endpoint. Otherwise, NULL.

## -remarks

The client driver can use this function to determine whether it has created a streams object for this endpoint. If it create the object the method returns the  UCXSSTREAMS handle. The method returns NULL if the object was not created, or if the client driver failed the framework request object passed in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback. Any call to this method must be matched by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereferencewithtag">WdfObjectDereferenceWithTag</a> by using the same Tag.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>

