---
UID: NS:dbgeng._STACK_SYM_FRAME_INFO
title: _STACK_SYM_FRAME_INFO (dbgeng.h)
description: Defines stack source information for an extended stack frame.
old-location: debugger\stack_sym_frame_info.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["STACK_SYM_FRAME_INFO structure"]
ms.keywords: "*PSTACK_SYM_FRAME_INFO, PSTACK_SYM_FRAME_INFO, PSTACK_SYM_FRAME_INFO structure pointer [Windows Debugging], STACK_SYM_FRAME_INFO, STACK_SYM_FRAME_INFO structure [Windows Debugging], _STACK_SYM_FRAME_INFO, dbgeng/PSTACK_SYM_FRAME_INFO, dbgeng/STACK_SYM_FRAME_INFO, debugger.stack_sym_frame_info"
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
req.typenames: STACK_SYM_FRAME_INFO, *PSTACK_SYM_FRAME_INFO
f1_keywords:
 - _STACK_SYM_FRAME_INFO
 - dbgeng/_STACK_SYM_FRAME_INFO
 - PSTACK_SYM_FRAME_INFO
 - dbgeng/PSTACK_SYM_FRAME_INFO
 - STACK_SYM_FRAME_INFO
 - dbgeng/STACK_SYM_FRAME_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dbgeng.h
api_name:
 - _STACK_SYM_FRAME_INFO
 - PSTACK_SYM_FRAME_INFO
 - STACK_SYM_FRAME_INFO
---

# _STACK_SYM_FRAME_INFO structure


## -description

Defines stack source information for an extended stack frame.

## -struct-fields

### -field StackFrameEx

A stack frame as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_stack_frame_ex">DEBUG_STACK_FRAME_EX</a> structure.

### -field SrcInfo

Stack source information as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_stack_src_info">STACK_SRC_INFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_stack_frame_ex">DEBUG_STACK_FRAME_EX</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_stack_src_info">STACK_SRC_INFO</a>

