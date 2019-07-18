---
UID: NF:netrequest.NetRequestGetType
title: NetRequestGetType function (netrequest.h)
description: Retrieves the request type in an OID request.
tech.root: netvista
ms.assetid: 3f9225b2-a6d3-41ca-abe3-97ed30620e14
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netrequest/NetRequestGetType"
ms.keywords: NetRequestGetType
req.header: netrequest.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequest.h
api_name: 
- NetRequestGetType
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRequestGetType function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Retrieves the request type in an OID request.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns a [NDIS_REQUEST_TYPE](../ntddndis/ne-ntddndis-_ndis_request_type.md) value that specifies the request type of the OID request.

## -remarks


## -see-also

[NDIS_OID_REQUEST](../ndis/ns-ndis-_ndis_oid_request.md)
