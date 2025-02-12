---
UID: NS:pktmonnpik._PKTMON_PACKET_CONTEXT_IN
tech.root: 
title: PKTMON_PACKET_CONTEXT_IN
ms.date: 02/12/2025
targetos: Windows
description: The PKTMON_PACKET_CONTEXT_IN struct is used to contain the packet context, which can represent a piece of data that is meaningful to the component, like a connection ID.
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
req.typenames: PKTMON_PACKET_CONTEXT_IN
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
 - _PKTMON_PACKET_CONTEXT_IN
 - PKTMON_PACKET_CONTEXT_IN
f1_keywords:
 - _PKTMON_PACKET_CONTEXT_IN
 - pktmonnpik/_PKTMON_PACKET_CONTEXT_IN
 - PKTMON_PACKET_CONTEXT_IN
 - pktmonnpik/PKTMON_PACKET_CONTEXT_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PACKET_CONTEXT_IN
---

## -description

The **PKTMON_PACKET_CONTEXT_IN** struct is used to contain the packet context, which can represent a piece of data that is meaningful to the component, like a connection ID.

## -struct-fields

### -field Header

Common header for version control.

### -field Id

Integer that is meaningful to the component, representing the type of data stored by fields *Value* and *Size*.

### -field Value

Pointer to the value stored in the packet context.

### -field Size

Size of the data pointed to by Value.

## -remarks

Currently only size 8 (sizeof(UINT64)) is supported. This implies that Value should point to a UINT64.

### -see-also

- [PktMonClntHeaderInfoLog](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfolog.md)
- [PktMonClntHeaderInfoDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfodrop.md)
