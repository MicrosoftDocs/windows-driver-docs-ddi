---
UID: NF:netrequest.NetRequestGetId
title: NetRequestGetId function (netrequest.h)
description: Retrieves the NDIS_OID identifier associated with the specified network request object.
tech.root: netvista
ms.assetid: 9e3bbfd8-0cc1-4d71-b648-c937b9e6b762
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netrequest/NetRequestGetId"
ms.keywords: NetRequestGetId
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
- NetRequestGetId
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRequestGetId function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Retrieves the NDIS_OID identifier associated with the specified network request object.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns the object identifier for the network request object. The value is an OID\_*XXX* code. 

## -remarks


## -see-also
