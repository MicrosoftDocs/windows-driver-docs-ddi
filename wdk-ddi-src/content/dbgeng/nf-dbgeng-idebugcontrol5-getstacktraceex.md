---
UID: NF:dbgeng.IDebugControl5.GetStackTraceEx
title: IDebugControl5::GetStackTraceEx method
author: windows-driver-content
description: The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see Debugging Optimized Code and Inline Functions.
old-location: debugger\idebugcontrol5_getstacktraceex.htm
old-project: debugger
ms.assetid: 6DFCA3CB-D5DE-4EF5-892B-776B932E6CE6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetStackTraceEx method [Windows Debugging], GetStackTraceEx method [Windows Debugging], IDebugControl5 interface, GetStackTraceEx,IDebugControl5.GetStackTraceEx, IDebugControl5, IDebugControl5 interface [Windows Debugging], GetStackTraceEx method, IDebugControl5::GetStackTraceEx, dbgeng/IDebugControl5::GetStackTraceEx, debugger.idebugcontrol5_getstacktraceex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl5.GetStackTraceEx
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl5::GetStackTraceEx method


## -description


The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.


## -syntax


````
HRESULT GetStackTraceEx(
  [in]            ULONG64               FrameOffset,
  [in]            ULONG64               StackOffset,
  [in]            ULONG64               InstructionOffset,
  [out]           PDEBUG_STACK_FRAME_EX Frames,
  [in]            ULONG                 FrameSize,
  [out, optional] PULONG                FramesFilled
);
````


## -parameters




### -param FrameOffset [in]

Specifies the location of the stack frame at the top of the stack.  If <i>FrameOffset</i> is set to zero, the current frame pointer is used instead.


### -param StackOffset [in]

Specifies the location of the current stack.  If <i>StackOffset</i> is set to zero, the current stack pointer is used instead.


### -param InstructionOffset [in]

Specifies the location of the instruction of interest for the function that is represented by the stack frame at the top of the stack.  If <i>InstructionOffset</i> is set to zero, the current instruction is used instead.


### -param Frames [out]

Receives the stack frames.  The number of elements this array holds is <i>FrameSize</i>.


### -param FramesSize




### -param FramesFilled [out, optional]

Receives the number of frames that were placed in the array <i>Frames</i>.  If <i>FramesFilled</i> is <b>NULL</b>, this information is not returned.


#### - FrameSize [in]

Specifies the number of items in the <i>Frames</i> array.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No stack frames were returned.

</td>
</tr>
</table>
 




## -remarks




    The stack trace returned to Frames can be printed using <a href="https://msdn.microsoft.com/library/windows/hardware/dn818567">OutputStackTraceEx</a>.


   




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn818567">OutputStackTraceEx</a>



<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>



<a href="..\wdbgexts\nc-wdbgexts-pwindbg_stacktrace_routine.md">StackTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn818564">GetContextStackTraceEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5::GetStackTraceEx method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

