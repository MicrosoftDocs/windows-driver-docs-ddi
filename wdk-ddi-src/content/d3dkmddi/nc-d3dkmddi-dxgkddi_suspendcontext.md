---
UID: NC:d3dkmddi.DXGKDDI_SUSPENDCONTEXT
title: DXGKDDI_SUSPENDCONTEXT (d3dkmddi.h)
description: Instruct the GPU to suspend a context.
ms.assetid: 05af5f3c-0884-4d16-9320-874a3e0a1b4d
ms.date: 10/19/2018
keywords: ["DXGKDDI_SUSPENDCONTEXT callback function"]
f1_keywords:
 - "d3dkmddi/DXGKDDI_SUSPENDCONTEXT"
 - "DXGKDDI_SUSPENDCONTEXT"
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
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DXGKDDI_SUSPENDCONTEXT
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# DXGKDDI_SUSPENDCONTEXT callback function

## -description

Instruct the GPU to suspend a context. If the GPU doesn’t acknowledge the suspend completion within the TDR (timeout detection and recovery) timeout, the OS will detect the engine timeout and perform engine reset.

## -prototype

```cpp
//Declaration

DXGKDDI_SUSPENDCONTEXT DxgkddiSuspendcontext;

// Definition

NTSTATUS DxgkddiSuspendcontext
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SUSPENDCONTEXT pSuspendContext
)
{...}

DXGKDDI_SUSPENDCONTEXT *PDXGKDDI_SUSPENDCONTEXT


```

## -parameters

### -param hAdapter

The hardware context to be preempted and marked as suspended. This type of preemption request does not have a grace period, and is expected to be honored by the GPU as soon as possible..

### -param pSuspendContext

Pointer to a [DXGKARG_SUSPENDCONTEXT](ns-d3dkmddi-_dxgkarg_suspendcontext.md) structure that contains a monotonically increasing per-context value that will be reported by the GPU context suspended interrupt once the preemption request is completed. Until the fence is signaled, the OS cannot assume GPU is suspended.

## -returns

Return STATUS_SUCCESS if the context is already suspended at the time of this call. Otherwise, this value is set to STATUS_PENDING, and the suspend operation will be finished when contextSuspendFence is signaled via an interrupt.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_SUSPENDCONTEXT and then calling DxgkddiSuspendContext.

Even though the round robin preemption can be initiated by the GPU, the OS still needs a way to preempt the context for other reasons, for example if it needs to move its allocations around, or perform a GPU power transition.

The context suspend value is necessary to handle cases when the OS suspends a context, doesn’t wait for the suspend acknowledgment, resumes, and suspends a context again. The suspend value will allow the OS to distinguish between the previous suspend acknowledgement and the latest one.

Once a context is suspended, it is assumed that all references to it are gone from the GPU, and the OS is free to destroy the context or move its memory around. Unlike WDDM 2.3 or earlier, no separate NULL context switch command (previously indicated by ContextSwitch flag in DdiSubmitCommandVirtual) is present in WDDM 2.4 scheduling mode, because DdiSuspendContext is supposed to do this work.

## -see-also
