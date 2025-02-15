---
UID: NC:pktmonclntk.PKTMON_CLNT_NBL_DROP
tech.root: netvista
title: PKTMON_CLNT_NBL_DROP
ms.date: 02/13/2025
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
 - PKTMON_CLNT_NBL_DROP
f1_keywords:
 - PKTMON_CLNT_NBL_DROP
 - pktmonclntk/PKTMON_CLNT_NBL_DROP
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_NBL_DROP
---

## -description

This callback function is invoked when a dropped network packet is logged. Additional information can be provided about why and where it got dropped.

## -parameters

### -param CompContext

Pointer to PKTMON_COMPONENT_CONTEXT which holds the context for the component.

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

### -param DropReason

Integer that indicates the reason for the packet to be dropped.

### -param LocationCode

Integer that indicates the location where the packet got dropped.

## -remarks

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
