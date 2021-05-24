---
UID: NS:gsotypes._NET_PACKET_GSO
tech.root: netvista
title: NET_PACKET_GSO
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The NET_PACKET_GSO structure contains Generic Segmentation Offload (GSO) information for a packet. 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: gsotypes.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: NET_PACKET_GSO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - gsotypes.h
api_name:
 - _NET_PACKET_GSO
 - NET_PACKET_GSO
f1_keywords:
 - _NET_PACKET_GSO
 - gsotypes/_NET_PACKET_GSO
 - NET_PACKET_GSO
 - gsotypes/NET_PACKET_GSO
dev_langs:
 - c++
---

## -description

The **NET_PACKET_GSO** structure contains [Generic Segmentation Offload (GSO)](/windows-hardware/drivers/netcx/gso-offload) information for a packet. 

## -struct-fields

### -field DUMMYUNIONNAME

A union that contains the TCP and UDP member.

### -field DUMMYUNIONNAME.TCP

A structure that holds the TCP GSO information.

### -field DUMMYUNIONNAME.TCP.Mss

The maximum segment size (MSS) for TCP segments.

### -field DUMMYUNIONNAME.TCP.Reserved0

Reserved for system use. Clients must not read or write this member.

### -field DUMMYUNIONNAME.UDP

A structure that holds the UDP GSO information.

### -field DUMMYUNIONNAME.UDP.Mss

The MSS for UDP segments.

### -field DUMMYUNIONNAME.UDP.Reserved0

Reserved for system use. Clients must not read or write this member.

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketGso**](../gso/nf-gso-netextensiongetpacketgso.md).

## -see-also

[Generic Segmentation Offload (GSO)](/windows-hardware/drivers/netcx/gso-offload)

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetPacketGso**](../gso/nf-gso-netextensiongetpacketgso.md)

