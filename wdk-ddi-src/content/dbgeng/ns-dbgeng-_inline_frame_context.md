---
UID: NS:dbgeng._INLINE_FRAME_CONTEXT
title: _INLINE_FRAME_CONTEXT (dbgeng.h)
description: Describes inline frame context.
old-location: debugger\inline_frame_context.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["INLINE_FRAME_CONTEXT structure"]
ms.keywords: INLINE_FRAME_CONTEXT, INLINE_FRAME_CONTEXT union [Windows Debugging], _INLINE_FRAME_CONTEXT, dbgeng/INLINE_FRAME_CONTEXT, debugger.inline_frame_context
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: INLINE_FRAME_CONTEXT
f1_keywords:
 - _INLINE_FRAME_CONTEXT
 - dbgeng/_INLINE_FRAME_CONTEXT
 - INLINE_FRAME_CONTEXT
 - dbgeng/INLINE_FRAME_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dbgeng.h
api_name:
 - _INLINE_FRAME_CONTEXT
 - INLINE_FRAME_CONTEXT
---

# _INLINE_FRAME_CONTEXT structure


## -description

Describes inline frame context.

## -struct-fields

### -field ContextValue

A context value.

### -field FrameId

### -field FrameType

### -field FrameSignature

 




#### - {
        BYTE FrameId;
        BYTE FrameType;
        WORD FrameSignature;
    }

A structure that contains frame context information.

