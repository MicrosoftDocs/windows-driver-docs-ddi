---
UID: NS:d3dkmddi._DXGKARG_SUSPENDCONTEXT
title: _DXGKARG_SUSPENDCONTEXT (d3dkmddi.h)
description: Arguments used in the DxgkddiSuspendContext callback function.
ms.date: 10/19/2018
keywords: ["DXGKARG_SUSPENDCONTEXT structure"]
ms.keywords: _DXGKARG_SUSPENDCONTEXT, DXGKARG_SUSPENDCONTEXT,
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
req.typenames: DXGKARG_SUSPENDCONTEXT
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARG_SUSPENDCONTEXT
 - d3dkmddi/_DXGKARG_SUSPENDCONTEXT
 - DXGKARG_SUSPENDCONTEXT
 - d3dkmddi/DXGKARG_SUSPENDCONTEXT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SUSPENDCONTEXT
dev_langs:
 - c++
---

# _DXGKARG_SUSPENDCONTEXT structure


## -description

Arguments used in the [DxgkddiSuspendContext](nc-d3dkmddi-dxgkddi_suspendcontext.md) callback function.

## -struct-fields

### -field hContext

The hardware context to be preempted and marked as suspended. This type of preemption request does not have a grace period, and is expected to be honored by the GPU as soon as possible.

### -field contextSuspendFence

A monotonically increasing per-context value that will be reported by the GPU context suspended interrupt once the preemption request is completed. Until the fence is signaled, the OS cannot assume GPU is suspended.

## -remarks

The context suspend fence value is necessary to handle cases when the OS suspends a context, doesn’t wait for the suspend fence acknowledgment, resumes, and suspends a context again. The suspend fence value will allow the OS to distinguish between the previous suspend acknowledgement and the latest one.

## -see-also

