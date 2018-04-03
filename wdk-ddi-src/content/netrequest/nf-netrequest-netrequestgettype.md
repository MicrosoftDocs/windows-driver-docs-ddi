---
UID: NF:netrequest.NetRequestGetType
title: NetRequestGetType function
author: windows-driver-content
description: Retrieves the request type in an OID request.
ms.assetid: 3f9225b2-a6d3-41ca-abe3-97ed30620e14
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequest.h
apiname: 
-	NetRequestGetType
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRequestGetType function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the request type in an OID request.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns a [NDIS_REQUEST_TYPE](../ntddndis/ne-ntddndis-_ndis_request_type.md) value that specifies the request type of the OID request.

## -remarks
The minimum NetAdapterCx version for **NetRequestGetType** is 1.0.

## -see-also

[NDIS_OID_REQUEST](../ndis/ns-ndis-_ndis_oid_request.md)