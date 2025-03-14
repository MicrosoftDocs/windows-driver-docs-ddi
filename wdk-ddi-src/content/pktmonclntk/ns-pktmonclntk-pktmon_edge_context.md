---
UID: NS:pktmonclntk._PKTMON_EDGE_CONTEXT
tech.root: netvista
title: PKTMON_EDGE_CONTEXT
ms.date: 03/14/2025
targetos: Windows
description: The PKTMON_EDGE_CONTEXT structure holds the context for an edge.
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
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_EDGE_CONTEXT
---

## -description

The **PKTMON_EDGE_CONTEXT** structure holds the context for an edge.

## -struct-fields

### -field ListLink

A **[LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry)** structure that is used to link the edge context to the list of edge contexts that belong to a component. Use *ListLink* to track all the edge contexts that belong to a component and to access these edge contexts.

### -field EdgeHandle

A handle to the edge.

### -field CompContext

A pointer to the **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** structure that holds the context for the component.

### -field PacketType

The **[PKTMON_PACKET_TYPE](ns-pktmonclntk-pktmon_packet_type.md)**.

## -remarks

## -see-also

- **[PKTMON_PACKET_TYPE](ns-pktmonclntk-pktmon_packet_type.md)**
- **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)**
