---
UID: NS:pktmondefk._PKTMON_IP_ADDRESS
tech.root: netvista
title: PKTMON_IP_ADDRESS
ms.date: 11/11/2025
targetos: Windows
description: The PKTMON_IP_ADDRESS structure represents an IP address in either IPv4 or IPv6 format for use in packet monitoring operations.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmondefk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames:
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmondefk.h
api_name:
 - _PKTMON_IP_ADDRESS
 - PKTMON_IP_ADDRESS
f1_keywords:
 - _PKTMON_IP_ADDRESS
 - pktmondefk/_PKTMON_IP_ADDRESS
 - PKTMON_IP_ADDRESS
 - pktmondefk/PKTMON_IP_ADDRESS
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_IP_ADDRESS
---

## -description

The **PKTMON_IP_ADDRESS** structure represents an IP address in either IPv4 or IPv6 format for use in packet monitoring operations. This structure provides a union that allows the same memory space to be interpreted as either an IPv4 address or an IPv6 address, enabling efficient storage and flexible access to IP address data when logging or filtering network packets.

## -struct-fields

### -field IPv4

Contains the IPv4 address as a single 32-bit value. This field is part of a union and shares memory with **IPv4_bytes**.

### -field IPv4_bytes[PKTMON_IPV4_ADDRESS_SIZE]

Contains the IPv4 address as an array of bytes. This field is part of a union and shares memory with **IPv4**, providing an alternative byte-level view of the same IPv4 address data.

### -field IPv6[2]

Contains the IPv6 address as an array of two 64-bit values. This field is part of a union and shares memory with **IPv6_bytes**.

### -field IPv6_bytes[PKTMON_IPV6_ADDRESS_SIZE]

Contains the IPv6 address as an array of bytes. This field is part of a union and shares memory with **IPv6**, providing an alternative byte-level view of the same IPv6 address data.

## -remarks

This structure is typically used as part of packet header information structures to represent local and remote IP addresses during packet monitoring operations. The union design allows developers to access the IP address data in the most convenient format for their use case—either as integer values or as byte arrays.

## -see-also

- [PKTMON_PACKET_HEADER_INFORMATION](../pktmonclntk/ns-pktmonclntk-pktmon_packet_header_information.md)
- [PKTMON_PACKET_HEADER_INFO](../pktmonclntnpik/ns-pktmonclntnpik-pktmon_packet_header_info.md)
- [PktMonClntHeaderInfoLog](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfolog.md)
