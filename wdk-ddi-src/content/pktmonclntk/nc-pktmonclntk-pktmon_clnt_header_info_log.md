---
UID: NC:pktmonclntk.PKTMON_CLNT_HEADER_INFO_LOG
tech.root: 
title: PKTMON_CLNT_HEADER_INFO_LOG
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
 - PKTMON_CLNT_HEADER_INFO_LOG
f1_keywords:
 - PKTMON_CLNT_HEADER_INFO_LOG
 - pktmonclntk/PKTMON_CLNT_HEADER_INFO_LOG
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_HEADER_INFO_LOG
---

## -description

This callback function is invoked when a network packet has flowed through (as opposed to being dropped) is logged. Like PktMonClntNblLog, this function is also used for packet logging but does not require NBLs. It can be useful when packet metadata needs to be logged.

## -parameters

### -param EdgeContext

Pointer to structure PKTMON_EDGE_CONTEXT which holds the edge context.

### -param PacketHeaderInformation

Pointer to structure PKTMON_PACKET_HEADER_INFORMATION containing the packet header information.

### -param Direction

Indicates the packet direction. Each component reports packets in two directions only (IN or OUT). Must be one of the values from PKTMON_DIRECTION enumeration.

### -param Context

Pointer to structure PKTMON_PACKET_CONTEXT_IN containing the packet context, which can represent a piece of data that is meaningful to the component, like a connection ID for example. Can be NULL.

## -remarks

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoDrop]()
