---
UID: NF:netpacket.NetPacketIsIpv6
title: NetPacketIsIpv6 function
description: The NetPacketIsIpv6 method determines if a NET_PACKET is an IPv6 packet. This method is reserved for system use. Do not call this method from your code.
tech.root: netvista
ms.assetid: dfb23a00-13fb-4c66-a950-8ec080dee7a5
ms.date: 03/12/2018
ms.topic: function
ms.keywords: NetPacketIsIpv6
req.header: netpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetPacketIsIpv6
product:
-	Windows
targetos: Windows

---

# NetPacketIsIpv6 function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The NetPacketIsIpv6 method determines if a [NET_PACKET](ns-netpacket-_net_packet.md) is an IPv6 packet. 

>[!WARNING]
> This method is reserved for system use. Do not call this method from your code.

## -parameters

### -param packet
A pointer to the [NET_PACKET](ns-netpacket-_net_packet.md).

## -returns
Returns **TRUE** if the packet is an IPv6 packet; false otherwise.

## -remarks


## -see-also
