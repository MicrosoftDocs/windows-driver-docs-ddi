---
UID: NS:netadapterpacket._NET_PACKET_CONTEXT_ATTRIBUTES
title: _NET_PACKET_CONTEXT_ATTRIBUTES
author: windows-driver-content
description: The NET_PACKET_CONTEXT_ATTRIBUTES structure represents attributes for a NET_PACKET context space.
ms.assetid: 6c8d8aa8-ece2-4ce7-8424-8e3f793c75b6
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_PACKET_CONTEXT_ATTRIBUTES, NET_PACKET_CONTEXT_ATTRIBUTES, *PNET_PACKET_CONTEXT_ATTRIBUTES, 
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_PACKET_CONTEXT_ATTRIBUTES, *PNET_PACKET_CONTEXT_ATTRIBUTES
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapterpacket.h
apiname: 
-	NET_PACKET_CONTEXT_ATTRIBUTES
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_PACKET_CONTEXT_ATTRIBUTES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_PACKET_CONTEXT_ATTRIBUTES** structure represents attributes for a NET_PACKET context space.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field ContextSizeOverride
If this member is not set to zero, it represents the context size to use when allocating the packet context.
 
### -field ContextTypeInfo
A pointer to a [WDF_OBJECT_CONTEXT_TYPE_INFO](../wdfobject/ns-wdfobject-_wdf_object_context_type_info.md) structure.

## -remarks
Initialize this structure with a context type by calling [NET_PACKET_CONTEXT_ATTRIBUTES_INIT_TYPE](nf-netadapterpacket-net_packet_context_attributes_init_type.md).



## -see-also