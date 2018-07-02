---
UID: NS:netpacket._NET_PACKET_LAYOUT
title: _NET_PACKET_LAYOUT
author: windows-driver-content
description: A NET_PACKET_LAYOUT structure describes the start of each protocol header in a NET_PACKET.
ms.assetid: 71300205-2332-4127-8622-86390FE54BBD
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_PACKET_LAYOUT, NET_PACKET_LAYOUT, *PNET_PACKET_LAYOUT, _NET_PACKET_LAYER2_TYPE, NET_PACKET_LAYER2_TYPE, _NET_PACKET_LAYER3_TYPE, NET_PACKET_LAYER3_TYPE, _NET_PACKET_LAYER4_TYPE, NET_PACKET_LAYER4_TYPE
req.header: netpacket.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_PACKET_LAYOUT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netpacket.h
apiname: 
-	NET_PACKET_LAYOUT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_PACKET_LAYOUT structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

A **NET_PACKET_LAYOUT** structure describes the start of each protocol header in a [NET_PACKET](ns-netpacket-_net_packet.md).

## -struct-fields

### -field Layer2Type
An enumeration that specifies a flag from **NET_PACKET_LAYER2_TYPE**.

```c++
typedef enum _NET_PACKET_LAYER2_TYPE
{
    NET_PACKET_LAYER2_TYPE_UNSPECIFIED                  = 0,
    NET_PACKET_LAYER2_TYPE_NULL                         = 1,
    NET_PACKET_LAYER2_TYPE_ETHERNET                     = 2,
} NET_PACKET_LAYER2_TYPE;
```

### -field Layer3Type
An enumeration that specifies a flag from NET_PACKET_LAYER3_TYPE.

```c++
typedef enum _NET_PACKET_LAYER3_TYPE
{
    NET_PACKET_LAYER3_TYPE_UNSPECIFIED                  = 0,
    NET_PACKET_LAYER3_TYPE_IPV4_UNSPECIFIED_OPTIONS     = 1,
    NET_PACKET_LAYER3_TYPE_IPV4_WITH_OPTIONS            = 2,
    NET_PACKET_LAYER3_TYPE_IPV4_NO_OPTIONS              = 3,
    NET_PACKET_LAYER3_TYPE_IPV6_UNSPECIFIED_EXTENSIONS  = 4,
    NET_PACKET_LAYER3_TYPE_IPV6_WITH_EXTENSIONS         = 5,
    NET_PACKET_LAYER3_TYPE_IPV6_NO_EXTENSIONS           = 6,
} NET_PACKET_LAYER3_TYPE;
```

### -field Layer4Type
An enumeration that specifies a flag from NET_PACKET_LAYER4_TYPE.

```c++
typedef enum _NET_PACKET_LAYER4_TYPE
{
    NET_PACKET_LAYER4_TYPE_UNSPECIFIED                  = 0,
    NET_PACKET_LAYER4_TYPE_TCP                          = 1,
    NET_PACKET_LAYER4_TYPE_UDP                          = 2,
    NET_PACKET_LAYER4_TYPE_IP_NOT_FRAGMENTED            = 3,
    NET_PACKET_LAYER4_TYPE_IP_FRAGMENT                  = 4,
} NET_PACKET_LAYER4_TYPE;
```

### -field Reserved
Reserved for system use.

### -field Layer2HeaderLength
The length in bytes of the Layer 2 header, or zero if the Layer 2 length is unknown.

### -field Layer3HeaderLength
The length in bytes of the Layer 3 header, or zero if the Layer 3 length is unknown.

### -field Layer4HeaderLength
The length of the Layer 4 header, or zero if the Layer 4 length is unknown.

## -remarks
For more info about using this structure, see the **Layout** member of [NET_PACKET](ns-netpacket-_net_packet.md).



## -see-also