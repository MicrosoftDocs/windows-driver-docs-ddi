---
UID: NF:netpacket.NET_PACKET_GET_FRAGMENT_VALID
title: NET_PACKET_GET_FRAGMENT_VALID macro
author: windows-driver-content
description: The NET_PACKET_GET_FRAGMENT_VALID macro checks if a NET_PACKET contains at least one valid NET_PACKET_FRAGMENT.
ms.assetid: f6886856-e79a-4fd6-9745-3b8c20387cc4
ms.author: windowsdriverdev
ms.date: 03/12/2018
ms.topic: macro
ms.keywords: NET_PACKET_GET_FRAGMENT_VALID
req.header: netpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: netpacket.h
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
-	netpacket.h
apiname: 
-	NET_PACKET_GET_FRAGMENT_VALID
product:
-	Windows
targetos: Windows

---

# NET_PACKET_GET_FRAGMENT_VALID macro


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_PACKET_GET_FRAGMENT_VALID** macro checks if a [NET_PACKET](ns-netpacket-_net_packet.md) contains at least one valid [NET_PACKET_FRAGMENT](ns-netpacket-_net_packet_fragment.md).

## -parameters

### -param packet
A pointer to a [NET_PACKET](ns-netpacket-_net_packet.md) structure.

## -remarks
The minimum version for **NET_PACKET_GET_FRAGMENT_VALID** is 1.2.

## -see-also