---
UID: NE:checksumtypes._NET_PACKET_TX_CHECKSUM_ACTION
title: NET_PACKET_TX_CHECKSUM_ACTION (checksumtypes.h)
author: windows-driver-content
description: The NET_PACKET_TX_CHECKSUM_ACTION enumeration specifies checksum action flags for a NET_PACKET_CHECKSUM structure during packet transmission.
tech.root: netvista
ms.assetid: 2d4005bc-13e3-462d-9e73-5f6cea707db3
ms.author: windowsdriverdev
ms.date: 09/25/2019
keywords: ["NET_PACKET_TX_CHECKSUM_ACTION enumeration"]
ms.keywords: NET_PACKET_TX_CHECKSUM_ACTION, NET_PACKET_TX_CHECKSUM_ACTION,
req.header: checksumtypes.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_PACKET_TX_CHECKSUM_ACTION
targetos: Windows
ms.custom: Vb
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - checksumtypes.h
api_name:
 - NET_PACKET_TX_CHECKSUM_ACTION
product:
 - Windows
f1_keywords:
 - _NET_PACKET_TX_CHECKSUM_ACTION
 - checksumtypes/_NET_PACKET_TX_CHECKSUM_ACTION
 - NET_PACKET_TX_CHECKSUM_ACTION
 - checksumtypes/NET_PACKET_TX_CHECKSUM_ACTION
---

# NET_PACKET_TX_CHECKSUM_ACTION enumeration


## -description

The **NET_PACKET_TX_CHECKSUM_ACTION** enumeration specifies checksum action flags for a [**NET_PACKET_CHECKSUM**](../checksumtypes/ns-checksumtypes-_net_packet_checksum.md) structure during packet transmission.

## -enum-fields

### -field NetPacketTxChecksumActionPassthrough 

Indicates the client should not perform checksum calculation for this layer.

### -field NetPacketTxChecksumActionRequired 

Indicates the client should perform checksum calculation for this layer.

## -remarks

## -see-also

[**NET_PACKET_CHECKSUM**](../checksumtypes/ns-checksumtypes-_net_packet_checksum.md)

