---
UID: NF:packet.NetPacketIsIpv6
title: NetPacketIsIpv6 function (packet.h)
description: The NetPacketIsIpv6 method determines if a NET_PACKET is an IPv6 packet. This method is reserved for system use. Do not call this method from your code.
tech.root: netvista
ms.assetid: dfb23a00-13fb-4c66-a950-8ec080dee7a5
ms.date: 01/30/2019
keywords: ["NetPacketIsIpv6 function"]
ms.keywords: NetPacketIsIpv6
req.header: packet.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: Any level as long as target memory is resident
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NetPacketIsIpv6
 - packet/NetPacketIsIpv6
topictype:
 - apiref
apitype:
 - DllExport
apilocation:
 - NtosKrnl.exe
apiname:
 - NetPacketIsIpv6
---

# NetPacketIsIpv6 function


## -description

The **NetPacketIsIpv6** method determines if a [**NET_PACKET**](ns-packet-_net_packet.md) is an IPv6 packet. 

>[!WARNING]
> This method is reserved for system use. Do not call this method from your code.

## -parameters

### -param packet

A pointer to a [**NET_PACKET**](ns-packet-_net_packet.md) structure.

## -returns

Returns **TRUE** if the packet is an IPv6 packet; false otherwise.

## -remarks

## -see-also

