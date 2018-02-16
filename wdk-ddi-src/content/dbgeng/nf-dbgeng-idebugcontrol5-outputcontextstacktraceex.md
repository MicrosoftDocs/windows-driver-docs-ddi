---
UID: NF:dbgeng.IDebugControl5.OutputContextStackTraceEx
title: IDebugControl5::OutputContextStackTraceEx method
author: windows-driver-content
description: The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts.
old-location: debugger\idebugcontrol5_outputcontextstacktraceex.htm
old-project: debugger
ms.assetid: B0C1E602-83CE-4F4E-9198-B1B1CDAFF4BF
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl5, OutputContextStackTraceEx method [Windows Debugging], IDebugControl5 interface, dbgeng/IDebugControl5::OutputContextStackTraceEx, OutputContextStackTraceEx, OutputContextStackTraceEx method [Windows Debugging], IDebugControl5 interface [Windows Debugging], OutputContextStackTraceEx method, debugger.idebugcontrol5_outputcontextstacktraceex, IDebugControl5::OutputContextStackTraceEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl5.OutputContextStackTraceEx
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl5::OutputContextStackTraceEx method


## -description


The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts. The OutputContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.


## -syntax


````
HRESULT OutputContextStackTraceEx(
  [in] ULONG                 OutputControl,
  [in] PDEBUG_STACK_FRAME_EX Frames,
  [in] ULONG                 FramesSize,
  [in] PVOID                 FrameContexts,
  [in] ULONG                 FrameContextsSize,
  [in] ULONG                 FrameContextsEntrySize,
  [in] ULONG                 Flags
);
````


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


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



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
 




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5::OutputContextStackTraceEx method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

