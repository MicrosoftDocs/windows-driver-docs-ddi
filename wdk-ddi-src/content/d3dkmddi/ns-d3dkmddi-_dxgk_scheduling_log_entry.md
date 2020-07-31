---
UID: NS:d3dkmddi._DXGK_SCHEDULING_LOG_ENTRY
title: _DXGK_SCHEDULING_LOG_ENTRY (d3dkmddi.h)
description: Contains information about a scheduling log entry.
ms.assetid: 66e7d724-9605-486a-b02a-62378cf95319
ms.date: 10/19/2018
keywords: ["_DXGK_SCHEDULING_LOG_ENTRY structure"]
f1_keywords:
 - "d3dkmddi/_DXGK_SCHEDULING_LOG_ENTRY"
 - "_DXGK_SCHEDULING_LOG_ENTRY"
ms.keywords: _DXGK_SCHEDULING_LOG_ENTRY, DXGK_SCHEDULING_LOG_ENTRY,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_SCHEDULING_LOG_ENTRY
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGK_SCHEDULING_LOG_ENTRY
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGK_SCHEDULING_LOG_ENTRY structure

## -description

Contains information about a scheduling log entry.

## -struct-fields

### -field ContextStateChange

Pointer to a [DXGK_SCHEDULING_LOG_CONTEXT_STATE_CHANGE](ns-d3dkmddi-_dxgk_scheduling_log_context_state_change.md) structure that contains information about a scheduling log context state change event.

### -field ReservedOperationData

The number of reserved operation data.

### -field GpuTimeStamp

The GPU time stamp.

### -field OperationType

Pointer to a [DXGK_SCHEDULING_LOG_OPERATION](ne-d3dkmddi-_dxgk_scheduling_log_operation.md) enumeration that contains information about a scheduling log operation.

### -field ReservedOperationTypeBits

The number of reserved operation type bits.

## -remarks

## -see-also
