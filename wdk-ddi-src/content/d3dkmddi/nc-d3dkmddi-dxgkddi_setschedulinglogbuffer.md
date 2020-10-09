---
UID: NC:d3dkmddi.DXGKDDI_SETSCHEDULINGLOGBUFFER
title: DXGKDDI_SETSCHEDULINGLOGBUFFER (d3dkmddi.h)
description: Instruct the GPU to use the passed buffer as a scheduling log for a particular GPU node.
ms.assetid: b999c9b3-7f29-4dae-9968-86fbcaa9fabb
ms.date: 10/19/2018
keywords: ["DXGKDDI_SETSCHEDULINGLOGBUFFER callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_SETSCHEDULINGLOGBUFFER
 - d3dkmddi/DXGKDDI_SETSCHEDULINGLOGBUFFER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETSCHEDULINGLOGBUFFER
---

# DXGKDDI_SETSCHEDULINGLOGBUFFER callback function


## -description

Instruct the GPU to use the passed buffer as a scheduling log for a particular GPU node.

## -parameters

### -param hAdapter

Identifies the logical adapter.

### -param pSetSchedulingLogBuffer

Pointer to a [DXGKARG_SETSCHEDULINGLOGBUFFER](ns-d3dkmddi-_dxgkarg_setschedulinglogbuffer.md) structure that contains information to set scheduling log buffer.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

DXGKDDI_SETSCHEDULINGLOGBUFFER DxgkddiSetschedulinglogbuffer;

// Definition

NTSTATUS DxgkddiSetschedulinglogbuffer
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SETSCHEDULINGLOGBUFFER pSetSchedulingLogBuffer
)
{...}

DXGKDDI_SETSCHEDULINGLOGBUFFER *PDXGKDDI_SETSCHEDULINGLOGBUFFER


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_SETSCHEDULINGLOGBUFFER and then calling DxgkddiSetSchedulingLogBuffer.

DxgkDdiSetSchedulingLogBuffer is a synchronous call. Upon the return from DxgkDdiSetSchedulingLogBuffer, the GPU is not allowed to write any more entries to the previous log. All new entries will be written to the log buffer passed by the latest DxgkDdiSetSchedulingLogBuffer call.

The log buffer passed by the OS has FirstFreeEntryIndex and WraparondCount set to zero, and NumberOfEntries set to the number of allocated log entries. The rest of the buffer is uninitialized. In particular, the GPU cannot assume the individual entries in the log entry buffer are zero initialized.

## -see-also

