---
UID: NS:dbgeng._INLINE_FRAME_CONTEXT
title: _INLINE_FRAME_CONTEXT
author: windows-driver-content
description: Describes inline frame context.
old-location: debugger\inline_frame_context.htm
old-project: debugger
ms.assetid: 6EB52227-8685-4096-882F-64550A84DE4F
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _INLINE_FRAME_CONTEXT, INLINE_FRAME_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: INLINE_FRAME_CONTEXT
req.alt-loc: Dbgeng.h
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
req.typenames: INLINE_FRAME_CONTEXT
---

# _INLINE_FRAME_CONTEXT structure



## -description
Describes inline frame context. 



## -syntax

````
typedef union _INLINE_FRAME_CONTEXT {
  DWORD  ContextValue;
  struct  {
        BYTE FrameId;
        BYTE FrameType;
        WORD FrameSignature;
    };
} INLINE_FRAME_CONTEXT;
````


## -struct-fields

### -field ContextValue

A context value. 


### -field {
        BYTE FrameId;
        WORD FrameSignature;
    }</b>

<dd>
A structure that contains frame context information.  


## -remarks
