---
UID: NS:pktmonclntk._PKTMON_COMPONENT_CONTEXT
tech.root: netvista
title: PKTMON_COMPONENT_CONTEXT
ms.date: 03/14/2025
targetos: Windows
description: The PKTMON_COMPONENT_CONTEXT structure holds the context for the component.
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
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_CONTEXT
---

## -description

The **PKTMON_COMPONENT_CONTEXT** structure holds the context for the component.

## -struct-fields

### -field ListLink

A **[LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry)** structure that links to the next component in the list.

### -field EdgeList

The list of edges for this component. An edge represents a pair of entry/exit points for a component.

### -field EdgeCount

The number of entries in *EdgeList*.

### -field CompHandle

The handle for the component.

### -field CompType

The type of the component.

### -field PacketType

The type of packet being handled by the component.

### -field FlowEnabled

Indicates if flow logging is enabled.

### -field DropEnabled

Indicates if dropped packet logging is enabled.

## -remarks

This structure should be zero-initialized before **[PktMonClntComponentRegister](nf-pktmonclntk-pktmonclntcomponentregister.md)** is called and **PktMonClntComponentRegister** will fill in the structure as needed.

## -see-also

- **[LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry)**
- **[PktMonClntComponentRegister](nf-pktmonclntk-pktmonclntcomponentregister.md)**
