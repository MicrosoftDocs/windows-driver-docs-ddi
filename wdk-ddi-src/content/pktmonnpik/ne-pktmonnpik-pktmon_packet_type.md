---
UID: NE:pktmonnpik._PKTMON_PACKET_TYPE
tech.root: netvista
title: PKTMON_PACKET_TYPE
ms.date: 02/19/2025
targetos: Windows
description: The PKTMON_PACKET_TYPE enum defines the various packet types that can be processed by Packet Monitor.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: pktmonnpik.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnpik.h
api_name:
 - _PKTMON_PACKET_TYPE
 - PKTMON_PACKET_TYPE
f1_keywords:
 - _PKTMON_PACKET_TYPE
 - pktmonnpik/_PKTMON_PACKET_TYPE
 - PKTMON_PACKET_TYPE
 - pktmonnpik/PKTMON_PACKET_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PACKET_TYPE
---

## -description

The **PKTMON_PACKET_TYPE** enum defines the various packet types that can be processed by Packet Monitor.

## -enum-fields

### -field PktMonPayload_Unknown

Corresponds to an unknown payload type.

### -field PktMonPayload_Ethernet

Corresponds to the Ethernet payload type.

### -field PktMonPayload_WiFi

Corresponds to the WiFi payload type.

### -field PktMonPayload_IP

Corresponds to the IP payload type.

### -field PktMonPayload_HTTP

Corresponds to the HTTP payload type.

### -field PktMonPayload_TCP

Corresponds to the TCP payload type.

### -field PktMonPayload_UDP

Corresponds to the UDP payload type.

### -field PktMonPayload_ARP

Corresponds to the ARP payload type.

### -field PktMonPayload_ICMP

Corresponds to the ICMP payload type.

### -field PktMonPayload_ESP

Corresponds to the ESP payload type.

### -field PktMonPayload_AH

Corresponds to the AH payload type.

### -field PktMonPayload_L4Payload

Corresponds to the L4Payload payload type.

## -remarks

## -see-also

- [PktMonClntComponentRegister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentregister.md)
