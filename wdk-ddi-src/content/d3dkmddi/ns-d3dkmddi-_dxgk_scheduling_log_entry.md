---
UID: NS:d3dkmddi._DXGK_SCHEDULING_LOG_ENTRY
title: _DXGK_SCHEDULING_LOG_ENTRY
author: windows-driver-content
description:
ms.assetid: 66e7d724-9605-486a-b02a-62378cf95319
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGK_SCHEDULING_LOG_ENTRY
product: Windows
targetos: Windows
---

# _DXGK_SCHEDULING_LOG_ENTRY structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Contains information about a scheduling log entry.

## -struct-fields

### -field ContextStateChange

Pointer to a DXGK_SCHEDULING_LOG_CONTEXT_STATE_CHANGE structure that contains information about a scheduling log context state change event.

### -field ReservedOperationData

The number of reserved operation data.

### -field GpuTimeStamp

The GPU time stamp.

### -field OperationType

Pointer to a DXGK_SCHEDULING_LOG_OPERATION structure that contains information about a scheduling log operation.

### -field ReservedOperationTypeBits

The number of reserved operation type bits.

## -remarks

## -see-also