---
UID: NS:pktmonclntk._PKTMON_COMPONENT_CONTEXT
tech.root: 
title: PKTMON_COMPONENT_CONTEXT
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
req.typenames: PKTMON_COMPONENT_CONTEXT
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
 - _PKTMON_COMPONENT_CONTEXT
 - PKTMON_COMPONENT_CONTEXT
f1_keywords:
 - _PKTMON_COMPONENT_CONTEXT
 - pktmonclntk/_PKTMON_COMPONENT_CONTEXT
 - PKTMON_COMPONENT_CONTEXT
 - pktmonclntk/PKTMON_COMPONENT_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_CONTEXT
---

## -description

This struct is used to hold the context for a component in the Packet Monitor.

## -struct-fields

### -field ListLink

Used to track all the edge contexts belonging to a component. ListLink can be used to access these edge contexts.

### -field EdgeList

The list of edges added to the component. An edge represents a pair of entry/exit points for a component.

### -field EdgeCount

The number of entries in *EdgeList*.

### -field CompHandle

Handle for the component.

### -field CompType

The type of the component.

### -field PacketType

The type of packet being handled by the component.

### -field FlowEnabled

Indicates if flow logging is enabled.

### -field DropEnabled

Indicates if dropped packet logging is enabled.

## -remarks

## -see-also
