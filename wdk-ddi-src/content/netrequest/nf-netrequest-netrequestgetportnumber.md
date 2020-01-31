---
UID: NF:netrequest.NetRequestGetPortNumber
title: NetRequestGetPortNumber function (netrequest.h)
description: Retrieves the port number for the network request object. 
tech.root: netvista
ms.assetid: edf2d400-bfde-4cec-8164-7908cc008cf2
ms.date: 02/08/2018
f1_keywords:
 - "netrequest/NetRequestGetPortNumber"
ms.keywords: NetRequestGetPortNumber
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
- NetRequestGetPortNumber
targetos: Windows
product:
- Windows
---

# NetRequestGetPortNumber function


## -description



Retrieves the port number for the network request object. 

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns the port number corresponding to the network request object. If the port is unknown or default, returns zero.

## -remarks


## -see-also

[NDIS_OID_REQUEST](../ndis/ns-ndis-_ndis_oid_request.md)
