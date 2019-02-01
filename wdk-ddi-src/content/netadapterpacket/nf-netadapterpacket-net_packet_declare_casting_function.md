---
UID: NF:netadapterpacket.NET_PACKET_DECLARE_CASTING_FUNCTION
title: NET_PACKET_DECLARE_CASTING_FUNCTION macro (netadapterpacket.h)
description: The NET_PACKET_DECLARE_CASTING_FUNCTION macro declares a casting function for a NET_PACKET context space. 
tech.root: netvista
ms.assetid: b422849e-6601-46d9-a07c-6e9f2cf48725
ms.date: 10/19/2018
ms.topic: macro
ms.keywords: NET_PACKET_DECLARE_CASTING_FUNCTION
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
-	NET_PACKET_DECLARE_CASTING_FUNCTION
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NET_PACKET_DECLARE_CASTING_FUNCTION macro


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_PACKET_DECLARE_CASTING_FUNCTION** macro declares a casting function for a [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) context space. 

> [!WARNING]
> This macro is reserved for NetAdapterCx. Client drivers must not call this macro directly. Instead, they should call [NET_PACKET_DECLARE_CONTEXT_TYPE_WITH_NAME](nf-netadapterpacket-net_packet_declare_context_type_with_name.md).

## -parameters

### -param _contexttype
Reserved.

### -param _castingfunction
Reserved.

## -remarks



## -see-also
