---
UID: NF:netadapter.NetAdapterSetLinkLayerMtuSize
title: NetAdapterSetLinkLayerMtuSize function (netadapter.h)
description: Sets the link layer maximum transfer unit size of the adapter.
tech.root: netvista
ms.assetid: 367f8b32-c11a-46e4-ba1d-35c8ae359230
ms.date: 02/06/2018
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterSetLinkLayerMtuSize"
ms.keywords: NetAdapterSetLinkLayerMtuSize
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NetAdapterSetLinkLayerMtuSize
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NetAdapterSetLinkLayerMtuSize
targetos: Windows
product:
- Windows
---

# NetAdapterSetLinkLayerMtuSize function


## -description



Sets the link layer maximum transfer unit size of the adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param MtuSize
The new size of the adapter's MTU, in bytes.

## -remarks
The client driver first sets MTU size by calling **NetAdapterSetLinkLayerMtuSize** when starting a net adapter, before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

The client driver can change the MTU size after [**NetAdapterStart**](nf-netadapter-netadapterstart.md) returns by calling this method again. Doing so causes all of the adapter's transmit (Tx) and receive (Rx) queues to be recreated.



## -see-also

[NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md)
