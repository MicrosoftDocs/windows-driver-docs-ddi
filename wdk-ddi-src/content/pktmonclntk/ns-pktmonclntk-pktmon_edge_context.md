---
UID: NS:pktmonclntk._PKTMON_EDGE_CONTEXT
tech.root: 
title: PKTMON_EDGE_CONTEXT
ms.date: 02/10/2025
targetos: Windows
description: 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_EDGE_CONTEXT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - _PKTMON_EDGE_CONTEXT
 - PKTMON_EDGE_CONTEXT
f1_keywords:
 - _PKTMON_EDGE_CONTEXT
 - pktmonclntk/_PKTMON_EDGE_CONTEXT
 - PKTMON_EDGE_CONTEXT
 - pktmonclntk/PKTMON_EDGE_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_EDGE_CONTEXT
---

## -description

This struct is used to store the context information for an edge in a Packet Monitor component.

## -struct-fields

### -field ListLink

Used to track all the edge contexts belonging to a component. ListLink can be used to access these edge contexts.

### -field EdgeHandle

Handle for the edge.

### -field CompContext

Pointer to the component context.

### -field PacketType

The type of packet being handled by the edge.

## -remarks

A component can have multiple edges, and *ListLink* is used to track all the edge contexts belonging to a component.

### -see-also

- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntHeaderInfoLog]()
