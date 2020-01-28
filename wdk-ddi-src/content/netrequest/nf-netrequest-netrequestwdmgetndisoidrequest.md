---
UID: NF:netrequest.NetRequestWdmGetNdisOidRequest
title: NetRequestWdmGetNdisOidRequest function (netrequest.h)
description: Retrieves the traditional WDM NDIS_OID_REQUEST structure for the NETREQUEST.
tech.root: netvista
ms.assetid: 12b97789-3b90-475a-ac7c-cb4a08e9dea3
ms.date: 02/08/2018
f1_keywords:
 - "netrequest/NetRequestWdmGetNdisOidRequest"
ms.keywords: NetRequestWdmGetNdisOidRequest
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
- NetRequestWdmGetNdisOidRequest
targetos: Windows
product:
- Windows
---

# NetRequestWdmGetNdisOidRequest function


## -description



Retrieves the traditional WDM [NDIS_OID_REQUEST](../ndis/ns-ndis-_ndis_oid_request.md) structure for the NETREQUEST.

## -parameters

### -param Request
A handle to a network request object.

## -returns
A pointer to the [NDIS_OID_REQUEST](../ndis/ns-ndis-_ndis_oid_request.md) structure.

## -remarks


## -see-also
