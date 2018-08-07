---
UID: NF:netadapterpacket.NetPacketGetContextFromToken
title: NetPacketGetContextFromToken function
author: windows-driver-content
description: Client drivers should not call this method directly. Instead, they should call an accessor method created by a call to NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME.
ms.assetid: 437a8acf-4f9b-4a82-a6f2-b815343c8f3e
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetPacketGetContextFromToken
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: DISPATCH_LEVEL
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
-	NetPacketGetContextFromToken
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetPacketGetContextFromToken function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Client drivers should not call this method directly. Instead, they should call an accessor method created by a call to [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](nf-netadapterpacket-net_packet_declare_context_type_with_name.md).

## -parameters

### -param Descriptor

Reserved.

### -param NetPacket
Reserved.

### -param Token
Reserved.

## -returns
This function returns a pointer to a NET_PACKET context.

## -remarks


## -see-also