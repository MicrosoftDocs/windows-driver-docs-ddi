---
UID: NS:dbgeng._INLINE_FRAME_CONTEXT
title: "_INLINE_FRAME_CONTEXT"
author: windows-driver-content
description: Describes inline frame context.
old-location: debugger\inline_frame_context.htm
old-project: debugger
ms.assetid: 6EB52227-8685-4096-882F-64550A84DE4F
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: INLINE_FRAME_CONTEXT, INLINE_FRAME_CONTEXT union [Windows Debugging], _INLINE_FRAME_CONTEXT, dbgeng/INLINE_FRAME_CONTEXT, debugger.inline_frame_context
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dbgeng.h
api_name:
-	INLINE_FRAME_CONTEXT
product: Windows
targetos: Windows
req.typenames: INLINE_FRAME_CONTEXT
---

# _INLINE_FRAME_CONTEXT structure


## -description


Describes inline frame context. 


## -struct-fields




### -field ContextValue

A context value. 


#### - {
        BYTE FrameId;
        BYTE FrameType;
        WORD FrameSignature;
    }

A structure that contains frame context information.  

