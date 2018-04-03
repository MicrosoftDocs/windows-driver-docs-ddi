---
UID: NE:d3dkmddi._DXGK_SCHEDULING_LOG_CONTEXT_STATE
title: _DXGK_SCHEDULING_LOG_CONTEXT_STATE
author: windows-driver-content
description:
ms.assetid: ec661384-328c-479c-9f9e-dd6b955ff3bb
ms.author: windowsdriverdev
ms.date:
ms.topic: enum
ms.keywords: _DXGK_SCHEDULING_LOG_CONTEXT_STATE, DXGK_SCHEDULING_LOG_CONTEXT_STATE,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: DXGK_SCHEDULING_LOG_CONTEXT_STATE
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGK_SCHEDULING_LOG_CONTEXT_STATE
product: Windows
targetos: Windows
---

# _DXGK_SCHEDULING_LOG_CONTEXT_STATE enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Describes that event to log when a context transitions between one of its execution states. Context state change events are often accompanied by more specific queue events that result in changing the context state.

## -enum-fields

### -field DXGK_SCHEDULING_LOG_CONTEXT_STATE_IDLE

The context is idle and there is no pending GPU work present on the context.

### -field DXGK_SCHEDULING_LOG_CONTEXT_STATE_RUNNING

The context is currently executing on the GPU.

### -field DXGK_SCHEDULING_LOG_CONTEXT_STATE_READY

The context has pending GPU work, but is not executing on the GPU.

### -field DXGK_SCHEDULING_LOG_CONTEXT_STATE_READY_STANDBY

The context is ready, and the GPU has been informed this context is next to be executed, but the context has not started running yet. This state is not strictly required to be supported by the GPU context management processor, but it is useful for reducing context switch latency.
