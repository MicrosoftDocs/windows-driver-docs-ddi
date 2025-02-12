---
UID: NC:pktmonclntk.PKTMON_CLNT_NBL_LOG
tech.root: 
title: PKTMON_CLNT_NBL_LOG
ms.date: 02/10/2025
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - pktmonclntk.h
api_name:
 - PKTMON_CLNT_NBL_LOG
f1_keywords:
 - PKTMON_CLNT_NBL_LOG
 - pktmonclntk/PKTMON_CLNT_NBL_LOG
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_NBL_LOG
---

## -description

This callback function is invoked when a network packet has flowed through an edge (as opposed to being dropped) is logged. EdgeContext identifies the edge at which the action was taken.

## -parameters

### -param EdgeContext

Pointer to structure PKTMON_EDGE_CONTEXT which holds the edge context.

### -param NetBufferList

Pointer to the NET_BUFFER_LIST structure.

### -param PacketType

The type of packet being logged. This must be one of the values defined in the PKTMON_PACKET_TYPE enumeration.

### -param PacketHeaderInformation

Pointer to structure PKTMON_PACKET_HEADER_INFORMATION containing the packet header information. Can be NULL.

### -param UseOnlyFirstNbl

When TRUE indicates that only the first NBL in NetBufferList should be used. Otherwise all NBLs are used.

### -param Direction

Indicates the packet direction. Each component reports packets in two directions only (IN or OUT). Must be one of the values from PKTMON_DIRECTION enumeration.

## -remarks

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
