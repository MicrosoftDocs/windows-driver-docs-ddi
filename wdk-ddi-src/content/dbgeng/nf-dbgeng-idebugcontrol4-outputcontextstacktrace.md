---
UID: NF:dbgeng.IDebugControl4.OutputContextStackTrace
title: IDebugControl4::OutputContextStackTrace (dbgeng.h)
description: The OutputContextStackTrace method prints the call stack specified by an array of stack frames and corresponding register contexts.
old-location: debugger\outputcontextstacktrace.htm
tech.root: debugger
ms.assetid: da3d19ab-258d-4214-8674-b35fec06534b
ms.date: 05/03/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],OutputContextStackTrace method, IDebugControl4.OutputContextStackTrace, IDebugControl4::OutputContextStackTrace, IDebugControl_6d7b3f4e-9b64-41f5-8d26-ba745fae5d43.xml, OutputContextStackTrace, OutputContextStackTrace method [Windows Debugging], OutputContextStackTrace method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::OutputContextStackTrace, debugger.outputcontextstacktrace
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl4.OutputContextStackTrace"
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
- IDebugControl4.OutputContextStackTrace
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::OutputContextStackTrace


## -description


The <b>OutputContextStackTrace</b> method prints the call stack specified by an array of stack frames and corresponding register contexts.


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Frames [in]

Specifies the array of stack frames to output.  The number of elements in this array is <i>FramesSize</i>.  If <i>Frames</i> is <b>NULL</b>, the current stack frame is used.


### -param FramesSize [in]

Specifies the number of frames to output.


### -param FrameContexts [in]

Specifies the register context for each frame in the stack.  The entries in this array correspond to the entries in the <i>Frames</i> array.  The type of the thread context is the CONTEXT structure for the target's effective processor.


### -param FrameContextsSize [in]

Specifies the size, in bytes, of the memory pointed to by <i>FrameContexts</i>.  The number of stack frames must equal the number of contexts, and <i>FrameContextsSize</i> must equal <i>FramesSize</i> multiplied by <i>FrameContextsEntrySize</i>.


### -param FrameContextsEntrySize [in]

Specifies the size, in bytes, of each frame context in <i>FrameContexts</i>.


### -param Flags [in]

Specifies bit flags that determine what information to output for each frame.  <i>Flags</i> can be any combination of values from the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_STACK_ARGUMENTS

</td>
<td>
Displays the first three pieces of stack memory at the frame of each call.  On platforms where arguments are passed on the stack, and the code for the frame uses stack arguments, these values will be the arguments to the function.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FUNCTION_INFO

</td>
<td>
Displays information about the function that corresponds to the frame.  This includes calling convention and frame pointer omission (FPO) information.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_SOURCE_LINE

</td>
<td>
Displays source line information for each frame of the stack trace.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_ADDRESSES

</td>
<td>
Displays the return address, previous frame address, and other relevant addresses for each frame.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_COLUMN_NAMES

</td>
<td>
Displays column names.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_NONVOLATILE_REGISTERS

</td>
<td>
Displays the non-volatile register context for each frame.  This is only meaningful for some platforms.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_NUMBERS

</td>
<td>
Displays frame numbers.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_PARAMETERS

</td>
<td>
Displays parameter names and values as given in symbol information.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_ADDRESSES_RA_ONLY

</td>
<td>
Displays just the return address in the stack frame addresses.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_MEMORY_USAGE

</td>
<td>
Displays the number of bytes that separate the frames.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_PARAMETERS_NEWLINE

</td>
<td>
Displays each parameter and its type and value on a new line.

</td>
</tr>
</table>
 


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
 




## -remarks



The array of stack frames can be obtained using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getcontextstacktrace">GetContextStackTrace</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getcontextstacktrace">GetContextStackTrace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputstacktrace">OutputStackTrace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/k--kb--kc--kd--kp--kp--kv--display-stack-backtrace-">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
 

 

