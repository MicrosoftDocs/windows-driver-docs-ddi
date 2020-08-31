---
UID: NS:packet._NET_PACKET_LAYOUT
title: _NET_PACKET_LAYOUT (packet.h)
description: A NET_PACKET_LAYOUT structure describes the start of each protocol header in a NET_PACKET.
tech.root: netvista
ms.assetid: 71300205-2332-4127-8622-86390FE54BBD
ms.date: 09/27/2019
keywords: ["NET_PACKET_LAYOUT structure"]
ms.keywords: _NET_PACKET_LAYOUT, NET_PACKET_LAYOUT, *PNET_PACKET_LAYOUT, _NET_PACKET_LAYER2_TYPE, NET_PACKET_LAYER2_TYPE, _NET_PACKET_LAYER3_TYPE, NET_PACKET_LAYER3_TYPE, _NET_PACKET_LAYER4_TYPE, NET_PACKET_LAYER4_TYPE
req.header: packet.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.alt-api: 
req.alt-loc: 
req.typenames: NET_PACKET_LAYOUT
targetos: Windows
f1_keywords:
 - _NET_PACKET_LAYOUT
 - packet/_NET_PACKET_LAYOUT
 - NET_PACKET_LAYOUT
 - packet/NET_PACKET_LAYOUT
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - packet.h
apiname:
 - NET_PACKET_LAYOUT
---

# _NET_PACKET_LAYOUT structure


## -description

A **NET_PACKET_LAYOUT** structure describes the start of each protocol header in a [**NET_PACKET**](ns-packet-_net_packet.md).

## -struct-fields

### -field Layer2HeaderLength

The length in bytes of the Layer 2 header, or zero if the Layer 2 length is unknown.

### -field Layer3HeaderLength

The length in bytes of the Layer 3 header, or zero if the Layer 3 length is unknown.

### -field Layer4HeaderLength

The length of the Layer 4 header, or zero if the Layer 4 length is unknown.

### -field Layer2Type

An enumeration that specifies a flag from **NET_PACKET_LAYER2_TYPE**.

```c++
typedef enum _NET_PACKET_LAYER2_TYPE
{
    NetPacketLayer2TypeUnspecified,
    NetPacketLayer2TypeNull,
    NetPacketLayer2TypeEthernet,
} NET_PACKET_LAYER2_TYPE;
```

### -field Layer3Type

An enumeration that specifies a flag from **NET_PACKET_LAYER3_TYPE**.

```c++
typedef enum _NET_PACKET_LAYER3_TYPE
{
    NetPacketLayer3TypeUnspecified,
    NetPacketLayer3TypeIPv4UnspecifiedOptions,
    NetPacketLayer3TypeIPv4WithOptions,
    NetPacketLayer3TypeIPv4NoOptions,
    NetPacketLayer3TypeIPv6UnspecifiedExtensions,
    NetPacketLayer3TypeIPv6WithExtensions,
    NetPacketLayer3TypeIPv6NoExtensions,
} NET_PACKET_LAYER3_TYPE;
```

### -field Layer4Type

An enumeration that specifies a flag from NET_PACKET_LAYER4_TYPE.

```c++
typedef enum _NET_PACKET_LAYER4_TYPE
{
    NetPacketLayer4TypeUnspecified,
    NetPacketLayer4TypeTcp,
    NetPacketLayer4TypeUdp,
    NetPacketLayer4TypeIPFragment,
    NetPacketLayer4TypeIPNotFragment,
} NET_PACKET_LAYER4_TYPE;
```

### -field Reserved0

Reserved for system use.

## -remarks

For more info about using this structure, see the **Layout** member of [**NET_PACKET**](ns-packet-_net_packet.md).

## -see-also

