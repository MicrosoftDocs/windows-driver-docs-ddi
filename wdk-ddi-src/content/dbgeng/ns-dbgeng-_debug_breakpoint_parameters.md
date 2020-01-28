---
UID: NS:dbgeng._DEBUG_BREAKPOINT_PARAMETERS
title: _DEBUG_BREAKPOINT_PARAMETERS (dbgeng.h)
description: The DEBUG_BREAKPOINT_PARAMETERS structure contains most of the parameters for describing a breakpoint.
old-location: debugger\debug_breakpoint_parameters.htm
tech.root: debugger
ms.assetid: e5c87c1c-8195-4476-84bc-5f18ad83d149
ms.date: 05/03/2018
ms.keywords: "*PDEBUG_BREAKPOINT_PARAMETERS, DEBUG_BREAKPOINT_PARAMETERS, DEBUG_BREAKPOINT_PARAMETERS structure [Windows Debugging], PDEBUG_BREAKPOINT_PARAMETERS, PDEBUG_BREAKPOINT_PARAMETERS structure pointer [Windows Debugging], Structures_ad5f0e1f-7d6f-498d-80a0-1275ca3cb016.xml, _DEBUG_BREAKPOINT_PARAMETERS, dbgeng/DEBUG_BREAKPOINT_PARAMETERS, dbgeng/PDEBUG_BREAKPOINT_PARAMETERS, debugger.debug_breakpoint_parameters"
f1_keywords:
 - "dbgeng/DEBUG_BREAKPOINT_PARAMETERS"
req.header: dbgeng.h
req.include-header: DbgEng.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- DbgEng.h
api_name:
- DEBUG_BREAKPOINT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEBUG_BREAKPOINT_PARAMETERS, *PDEBUG_BREAKPOINT_PARAMETERS
---

# _DEBUG_BREAKPOINT_PARAMETERS structure


## -description


The DEBUG_BREAKPOINT_PARAMETERS structure contains most of the parameters for describing a breakpoint.


## -struct-fields




### -field Offset

The location in the target's memory address space that will trigger the breakpoint.  If the breakpoint is deferred (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getflags">GetFlags</a>), <b>Offset</b> is DEBUG_INVALID_OFFSET.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getoffset">GetOffset</a>.


### -field Id

The breakpoint ID.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getid">GetId</a>.


### -field BreakType

Specifies if the breakpoint is a software breakpoint or a processor breakpoint.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>.


### -field ProcType

The processor type for which the breakpoint is set.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>.


### -field Flags

The flags for the breakpoint.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getflags">GetFlags</a>.


### -field DataSize

The size, in bytes, of the memory block whose access will trigger the breakpoint.  If the type of the breakpoint is not a data breakpoint, this is zero.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getdataparameters">GetDataParameters</a>.


### -field DataAccessType

The type of access that will trigger the breakpoint.  If the type of the breakpoint is not a data breakpoint, this is zero.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getdataparameters">GetDataParameters</a>.


### -field PassCount

The number of times the target will hit the breakpoint before it is triggered.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getpasscount">GetPassCount</a>.


### -field CurrentPassCount

The remaining number of times that the target will hit the breakpoint before it is triggered.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getcurrentpasscount">GetCurrentPassCount</a>.


### -field MatchThread

The engine thread ID of the thread that can trigger this breakpoint.  If any thread can trigger this breakpoint, <b>MatchThread</b> is DEBUG_ANY_ID.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getmatchthreadid">GetMatchThreadId</a>.


### -field CommandSize

The size, in characters, of the command string that will be executed when the breakpoint is triggered.  If no command is set, <b>CommandSize</b> is zero.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getcommand">GetCommand</a>.


### -field OffsetExpressionSize

The size, in characters, of the expression string that evaluates to the location in the target's memory address space where the breakpoint is triggered.  If no expression string is set, <b>OffsetExpressionSize</b> is zero.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getoffsetexpression">GetOffsetExpression</a>.


## -remarks



For an overview of how to use breakpoints, and a description of all breakpoint-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/breakpoints3">Breakpoints</a>.



