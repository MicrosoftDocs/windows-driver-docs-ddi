---
UID: NS:lsotypes._NET_PACKET_LSO
title: NET_PACKET_LSO (lsotypes.h)
author: windows-driver-content
description: The NET_PACKET_LSO structure contains large send offload (LSO) information for a packet.
tech.root: netvista
ms.assetid: dbdc4d6d-06fb-45aa-8792-1bef0538b0d1
ms.author: windowsdriverdev
ms.date: 09/23/2019
f1_keywords:
 - "lsotypes/_NET_PACKET_LSO"
ms.keywords: NET_PACKET_LSO, NET_PACKET_LSO, 
req.header: lsotypes.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_PACKET_LSO
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - lsotypes.h
api_name: 
 - NET_PACKET_LSO
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_PACKET_LSO structure

## -description

The **NET_PACKET_LSO** structure contains large send offload (LSO) information for a packet.

## -struct-fields

### -field DUMMYUNIONNAME

A union that contains the **TCP** member.
 
### -field DUMMYUNIONNAME.TCP

A structure that holds the TCP LSO information.
 
### -field DUMMYUNIONNAME.TCP.Mss

The maximum segment size (MSS) for TCP segments.
 
### -field DUMMYUNIONNAME.TCP.Reserved0
 
Reserved for system use. Clients must not read or write this member.

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketLso**](../lso/nf-lso-netextensiongetpacketlso.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
