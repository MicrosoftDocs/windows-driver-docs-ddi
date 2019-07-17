---
UID: NE:d3dkmddi._DXGK_SCHEDULING_LOG_CONTEXT_STATE
title: _DXGK_SCHEDULING_LOG_CONTEXT_STATE (d3dkmddi.h)
description: Describes that event to log when a context transitions between one of its execution states.
ms.assetid: ec661384-328c-479c-9f9e-dd6b955ff3bb
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3dkmddi/_DXGK_SCHEDULING_LOG_CONTEXT_STATE"
ms.keywords: _DXGK_SCHEDULING_LOG_CONTEXT_STATE, DXGK_SCHEDULING_LOG_CONTEXT_STATE,
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
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGK_SCHEDULING_LOG_CONTEXT_STATE
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _DXGK_SCHEDULING_LOG_CONTEXT_STATE enumeration

## -description

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
