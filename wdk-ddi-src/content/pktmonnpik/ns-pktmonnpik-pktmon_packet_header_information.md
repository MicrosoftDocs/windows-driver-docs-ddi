---
UID: NS:pktmonnpik._PKTMON_PACKET_HEADER_INFORMATION
tech.root: netvista
title: PKTMON_PACKET_HEADER_INFORMATION
ms.date: 02/19/2025
targetos: Windows
description: The PKTMON_PACKET_HEADER_INFORMATION struct contains the packet header information.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_PACKET_HEADER_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnpik.h
api_name:
 - _PKTMON_PACKET_HEADER_INFORMATION
 - PKTMON_PACKET_HEADER_INFORMATION
f1_keywords:
 - _PKTMON_PACKET_HEADER_INFORMATION
 - pktmonnpik/_PKTMON_PACKET_HEADER_INFORMATION
 - PKTMON_PACKET_HEADER_INFORMATION
 - pktmonnpik/PKTMON_PACKET_HEADER_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PACKET_HEADER_INFORMATION
---

## -description

The **PKTMON_PACKET_HEADER_INFORMATION** struct contains the packet header information.

## -struct-fields

### -field SockAddrLocal

The local socket address.

### -field SockAddrRemote

The remote socket address.

### -field IpProtocol

The IP protocol.

### -field Transport

The transport protocol.

### -field Transport.Udp

### -field Transport.Udp.PortLocal

### -field Transport.Udp.PortRemote

### -field Transport.Tcp

### -field Transport.Tcp.PortLocal

### -field Transport.Tcp.PortRemote

### -field Transport.Tcp.Flags

### -field Transport.Icmp

### -field Transport.Icmp.Type

### -field Transport.Icmp.Code

### -field _PKTMON_TRANSPORT_PROTOCOL

## -remarks

## -see-also

- [PktMonClntNblLog](../pktmonclntk/nf-pktmonclntk-pktmonclntnbllog.md)
- [PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntnbldrop.md)
- [PktMonClntHeaderInfoLog](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfolog.md)
- [PktMonClntHeaderInfoDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfodrop.md)
