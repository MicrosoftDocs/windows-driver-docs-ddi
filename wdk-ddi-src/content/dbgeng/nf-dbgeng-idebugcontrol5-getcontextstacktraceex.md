---
UID: NF:dbgeng.IDebugControl5.GetContextStackTraceEx
title: IDebugControl5::GetContextStackTraceEx (dbgeng.h)
description: The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.
old-location: debugger\idebugcontrol5_getcontextstacktraceex.htm
tech.root: debugger
ms.assetid: 26B191ED-A38B-412D-93C3-E9A55216F91E
ms.date: 05/03/2018
ms.keywords: GetContextStackTraceEx, GetContextStackTraceEx method [Windows Debugging], GetContextStackTraceEx method [Windows Debugging],IDebugControl5 interface, IDebugControl5 interface [Windows Debugging],GetContextStackTraceEx method, IDebugControl5.GetContextStackTraceEx, IDebugControl5::GetContextStackTraceEx, dbgeng/IDebugControl5::GetContextStackTraceEx, debugger.idebugcontrol5_getcontextstacktraceex
f1_keywords:
 - "dbgeng/IDebugControl5.GetContextStackTraceEx"
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
req.target-type: Desktop
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
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl5.GetContextStackTraceEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl5::GetContextStackTraceEx


## -description


The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/changing-contexts">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-optimized-code-and-inline-functions-external">Debugging Optimized Code and Inline Functions</a>.


## -parameters




### -param StartContext [in, optional]

Specifies the register context for the top of the stack.


### -param StartContextSize [in]

Specifies the size, in bytes, of the <i>StartContext</i> register context.


### -param Frames [out, optional]

Receives the stack frames.  The number of elements this array holds is <i>FrameSize</i>.  If <i>Frames</i> is <b>NULL</b>, this information is not returned.


### -param FramesSize [in]

Specifies the number of items in the array <i>Frames</i>.


### -param FrameContexts [out, optional]

Receives the reconstructed register context for each frame in the stack.  The entries in this array correspond to the entries in the <i>Frames</i> array.  The type of the thread context is the CONTEXT structure for the target's effective processor.  If <i>FrameContexts</i> is <b>NULL</b>, this information is not returned.


### -param FrameContextsSize [in]

Specifies the size, in bytes, of the memory pointed to by <i>FrameContexts</i>.  The number of stack frames returned equals the number of contexts returned, and <i>FrameContextsSize</i> must equal <i>FramesSize</i> times <i>FrameContextsEntrySize</i>.


### -param FrameContextsEntrySize [in]

Specifies the size, in bytes, of each frame context in <i>FrameContexts</i>.


### -param FramesFilled [out, optional]

Receives the number of frames that were placed in the array <i>Frames</i> and contexts in <i>FrameContexts</i>.  If <i>FramesFilled</i> is <b>NULL</b>, this information is not returned.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



The stack trace returned to <i>Frames</i> and <i>FrameContexts</i> can be printed using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-outputcontextstacktraceex">OutputContextStackTraceEx</a>.

It is common for stack unwinds to restore only a subset of the registers.  For example, stack unwinds will not always restore the volatile register state because the volatile registers are scratch registers and code does not need to preserve them.  Registers that are not restored on unwind are left as the last value restored, so care should be taken when using the register state that might not be restored by an unwind. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getstacktraceex">GetStackTraceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol5">IDebugControl5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-outputcontextstacktraceex">OutputContextStackTraceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/k--kb--kc--kd--kp--kp--kv--display-stack-backtrace-">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
 

 

