---
UID: NS:d3dkmddi._DXGKARG_SETSCHEDULINGLOGBUFFER
title: _DXGKARG_SETSCHEDULINGLOGBUFFER
author: windows-driver-content
description:
ms.assetid: 717395a0-86b7-4945-b3bf-c991e1c97406
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_SETSCHEDULINGLOGBUFFER, DXGKARG_SETSCHEDULINGLOGBUFFER,
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
req.typenames: DXGKARG_SETSCHEDULINGLOGBUFFER
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGKARG_SETSCHEDULINGLOGBUFFER
product: Windows
targetos: Windows
---

# _DXGKARG_SETSCHEDULINGLOGBUFFER structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Arguments used in the call to [DxgkddiSetSchedulingLogBuffer](nc-d3dkmddi-dxgkddi_setschedulinglogbuffer.md).

## -struct-fields

### -field NodeOrdinal

The node ordinal.

### -field EngineOrdinal

 The engine ordinal.

### -field NumberOfEntries

The number of entries in the log entries array.

### -field LogBufferCpuVa

Kernel mode CPU VA of the log buffer.

### -field LogBufferGpuVa

GPU VA of the log buffer.

### -field InterruptEntry

Index of entry to raise interrupt when writing to.


## -see-also

[DxgkddiSetSchedulingLogBuffer](nc-d3dkmddi-dxgkddi_setschedulinglogbuffer.md)