---
UID: NF:netadapter.NetAdapterSetLinkLayerMtuSize
title: NetAdapterSetLinkLayerMtuSize function
author: windows-driver-content
description: Sets the link layer maximum transfer unit size of the adapter.
ms.assetid: 367f8b32-c11a-46e4-ba1d-35c8ae359230
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterSetLinkLayerMtuSize
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetAdapterSetLinkLayerMtuSize function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Sets the link layer maximum transfer unit size of the adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param MtuSize
The new size of the adapter's MTU, in bytes.

## -returns
This method does not return a value.

## -remarks
The client driver first sets MTU size by calling **NetAdapterSetLinkLayerMtuSize** from its *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)* implementation.

The client driver can change the MTU size after returning from *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)* by calling this method again. Doing so causes all of the adapter's transmit (Tx) and receive (Rx) queues to be recreated.



## -see-also

[NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md)