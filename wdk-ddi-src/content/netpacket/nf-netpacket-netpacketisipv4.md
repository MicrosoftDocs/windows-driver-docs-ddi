---
UID: NF:netpacket.NetPacketIsIpv4
title: NetPacketIsIpv4 function
author: windows-driver-content
description: The NetPacketIsIpv4 method determines if a NET_PACKET is an IPv4 packet. This method is reserved for system use. Do not call this method from your code.
ms.assetid: 2a7f93ae-f0a5-430f-adbb-e452ea9aa3ee
ms.author: windowsdriverdev
ms.date: 03/12/2018
ms.topic: function
ms.keywords: NetPacketIsIpv4
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
-	NetPacketIsIpv4
product: Windows
targetos: Windows

---

# NetPacketIsIpv4 function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The NetPacketIsIpv4 method determines if a [NET_PACKET](ns-netpacket-_net_packet.md) is an IPv4 packet. 

>[!WARNING]
> This method is reserved for system use. Do not call this method from your code.

## -parameters

### -param packet
A pointer to the [NET_PACKET](ns-netpacket-_net_packet.md).

## -returns
Returns **TRUE** if the packet is an IPv4 packet; false otherwise.

## -remarks


## -see-also