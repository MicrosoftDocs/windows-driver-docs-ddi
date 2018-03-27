---
UID: NS:d3dkmddi._DXGKARG_SUSPENDCONTEXT
title: _DXGKARG_SUSPENDCONTEXT
author: windows-driver-content
description:
ms.assetid: 3ca4dc90-55b2-4b5d-8f58-0967e817a26d
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGKARG_SUSPENDCONTEXT
product: Windows
targetos: Windows
---

# _DXGKARG_SUSPENDCONTEXT structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Arguments used in the [DxgkddiSuspendContext](nc-d3dkmddi-dxgkddi_suspendcontext.md) callback function.

## -struct-fields

### -field hContext

The hardware context to be preempted and marked as suspended. This type of preemption request does not have a grace period, and is expected to be honored by the GPU as soon as possible.

### -field contextSuspendFence

A monotonically increasing per-context value that will be reported by the GPU context suspended interrupt once the preemption request is completed. Until the fence is signaled, the OS cannot assume GPU is suspended.

## -remarks

The context suspend fence value is necessary to handle cases when the OS suspends a context, doesn’t wait for the suspend fence acknowledgment, resumes, and suspends a context again. The suspend fence value will allow the OS to distinguish between the previous suspend acknowledgement and the latest one.

## -see-also