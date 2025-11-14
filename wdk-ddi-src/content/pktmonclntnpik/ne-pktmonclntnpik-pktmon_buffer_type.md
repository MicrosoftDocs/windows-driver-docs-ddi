---
UID: NE:pktmonclntnpik._PKTMON_BUFFER_TYPE
tech.root: netvista
title: PKTMON_BUFFER_TYPE
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_BUFFER_TYPE enumeration defines the types of packet buffers that can be monitored by the Packet Monitor infrastructure.
ai-usage: ai-assisted
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: pktmonclntnpik.h
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
 - pktmonclntnpik.h
api_name:
 - _PKTMON_BUFFER_TYPE
 - PKTMON_BUFFER_TYPE
f1_keywords:
 - _PKTMON_BUFFER_TYPE
 - pktmonclntnpik/_PKTMON_BUFFER_TYPE
 - PKTMON_BUFFER_TYPE
 - pktmonclntnpik/PKTMON_BUFFER_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_BUFFER_TYPE
---

## -description

The **PKTMON_BUFFER_TYPE** enumeration defines the types of packet buffers that can be monitored by the Packet Monitor infrastructure. This enumeration specifies the format in which packet data is provided to the monitoring system.

## -enum-fields

### -field PktMonBuffer_NblChain

Indicates that the packet buffer is a chain of NET_BUFFER_LIST structures. This is used for monitoring multiple linked network buffers.

### -field PktMonBuffer_NblSingle

Indicates that the packet buffer is a single NET_BUFFER_LIST structure. This is the most common buffer type for monitoring individual network packets.

### -field PktMonBuffer_Wsk_Buf

Indicates that the packet buffer is a Winsock Kernel (WSK) buffer. This buffer type is used for monitoring socket-level packet data.

### -field PktMonBuffer_None

Indicates that no packet buffer is provided. This is used when only packet header information is being logged without the actual packet data.

## -remarks

Components specify the buffer type when logging packets using functions like **[PktMonClntNblLog](../pktmonclntk/nf-pktmonclntk-pktmonclntnbllog.md)** or **[PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntnbldrop.md)**. The buffer type helps the monitoring infrastructure correctly interpret and process the packet data.

## -see-also

- [PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)
- [PktMonClntNblLog](../pktmonclntk/nf-pktmonclntk-pktmonclntnbllog.md)
- [PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntnbldrop.md)
