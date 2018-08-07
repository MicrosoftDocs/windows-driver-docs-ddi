---
UID: NF:netadapterpacket.NetPacketGetTypedContext
title: NetPacketGetTypedContext function
author: windows-driver-content
description: Client drivers should not call this function directly. Instead, use NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME.
ms.assetid: 55dd1de1-b7af-4d16-8df3-010b74353de4
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetPacketGetTypedContext
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapterpacket.h
apiname: 
-	NetPacketGetTypedContext
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetPacketGetTypedContext function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Client drivers should not call this function directly. Instead, use [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](nf-netadapterpacket-net_packet_declare_context_type_with_name.md).

## -parameters

### -param Descriptor
Reserved.

### -param NetPacket
Reserved.

### -param TypeInfo
Reserved.

## -returns

Returns a pointer to the packet's context space.

## -remarks



## -see-also

[NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](nf-netadapterpacket-net_packet_declare_context_type_with_name.md)