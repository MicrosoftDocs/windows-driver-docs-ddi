---
UID: NS:pktmonclntnpik._PKTMON_PACKET_HEADER_INFO
tech.root: netvista
title: PKTMON_PACKET_HEADER_INFO
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PACKET_HEADER_INFO structure contains parsed packet header information for network and transport layer protocols.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_PACKET_HEADER_INFO
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntnpik.h
api_name:
 - _PKTMON_PACKET_HEADER_INFO
 - PKTMON_PACKET_HEADER_INFO
f1_keywords:
 - _PKTMON_PACKET_HEADER_INFO
 - pktmonclntnpik/_PKTMON_PACKET_HEADER_INFO
 - PKTMON_PACKET_HEADER_INFO
 - pktmonclntnpik/PKTMON_PACKET_HEADER_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PACKET_HEADER_INFO
---

## -description

The **PKTMON_PACKET_HEADER_INFO** structure contains parsed packet header information for network and transport layer protocols. This structure provides detailed information about IP addresses, protocols, and transport-specific details (TCP, UDP, or ICMP).

## -struct-fields

### -field AddrFamily

The address family of the packet, indicating whether it uses IPv4 or IPv6.

### -field IpAddrLocal

A **[PKTMON_IP_ADDRESS](../pktmondefk/ns-pktmondefk-pktmon_ip_address.md)** structure containing the local IP address.

### -field IpAddrRemote

A **[PKTMON_IP_ADDRESS](../pktmondefk/ns-pktmondefk-pktmon_ip_address.md)** structure containing the remote IP address.

### -field IpProtocol

The IP protocol number (e.g., 6 for TCP, 17 for UDP, 1 for ICMP).

### -field Transport

A union containing transport-layer specific information.

### -field Transport.Udp

A structure containing UDP-specific fields.

### -field Transport.Udp.PortLocal

The local UDP port number.

### -field Transport.Udp.PortRemote

The remote UDP port number.

### -field Transport.Tcp

A structure containing TCP-specific fields.

### -field Transport.Tcp.PortLocal

The local TCP port number.

### -field Transport.Tcp.PortRemote

The remote TCP port number.

### -field Transport.Tcp.Flags

TCP flags (e.g., SYN, ACK, FIN).

### -field Transport.Icmp

A structure containing ICMP-specific fields.

### -field Transport.Icmp.Type

The ICMP message type.

### -field Transport.Icmp.Code

The ICMP message code.

### -field _PKTMON_TRANSPORT

The name of the transport union type.

## -remarks

This structure is used within **[PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)** to provide parsed header information when logging packets.

## -see-also

- [PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)
- [PKTMON_IP_ADDRESS](../pktmondefk/ns-pktmondefk-pktmon_ip_address.md)
- [PktMonClntHeaderInfoLog](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfolog.md)

