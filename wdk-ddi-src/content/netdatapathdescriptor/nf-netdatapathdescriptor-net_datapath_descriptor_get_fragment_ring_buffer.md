---
UID: NF:netdatapathdescriptor.NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER
title: NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER macro
author: windows-driver-content
description: The NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER macro retrieves a datapath queue's fragment ring buffer.
ms.assetid: 2bbf1079-abf9-4980-8b99-f392bbdfaa43
ms.author: windowsdriverdev
ms.date: 02/27/2018
ms.topic: macro
ms.keywords: NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER
req.header: netdatapathdescriptor.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: netdatapathdescriptor.h
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netdatapathdescriptor.h
apiname: 
-	NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER
product: Windows
targetos: Windows

---

# NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER macro


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_DATAPATH_DESCRIPTOR_GET_FRAGMENT_RING_BUFFER** macro retrieves a datapath queue's fragment ring buffer.

## -parameters

### -param rbs
A pointer to the queue's [NET_DATAPATH_DESCRIPTOR](ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

## -remarks
Client drivers do not call this macro to access the fragment ring buffer directly. Instead, they can access a fragment with a call to [NET_PACKET_GET_FRAGMENT](nf-netdatapathdescriptor-net_packet_get_fragment.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)