---
UID: NF:dbgeng.IDebugControl3.GetStackTrace
title: IDebugControl3::GetStackTrace method
author: windows-driver-content
description: The GetStackTrace method returns the frames at the top of the specified call stack.
old-location: debugger\getstacktrace.htm
old-project: debugger
ms.assetid: 2d07e6a3-b560-4d9b-aece-0368d5929867
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetStackTrace, GetStackTrace
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
req.alt-api: IDebugControl.GetStackTrace,IDebugControl2.GetStackTrace,IDebugControl3.GetStackTrace
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::GetStackTrace method



## -description
The <b>GetStackTrace</b> method returns the frames at the top of the specified call stack.



## -syntax

````
HRESULT GetStackTrace(
  [in]            ULONG64            FrameOffset,
  [in]            ULONG64            StackOffset,
  [in]            ULONG64            InstructionOffset,
  [out]           PDEBUG_STACK_FRAME Frames,
  [in]            ULONG              FrameSize,
  [out, optional] PULONG             FramesFilled
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


### -param FrameSize [in]

Specifies the number of items in the <i>Frames</i> array.


### -param FramesFilled [out, optional]

Receives the number of frames that were placed in the array <i>Frames</i>.  If <i>FramesFilled</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>No stack frames were returned.

 


## -remarks
The stack trace returned to <i>Frames</i> can be printed using <a href="https://msdn.microsoft.com/library/windows/hardware/ff553252">OutputStackTrace</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545748">GetContextStackTrace</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553252">OutputStackTrace</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
</dt>
<dt>
<a href="..\wdbgexts\nc-wdbgexts-pwindbg_stacktrace_routine.md">StackTrace</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetStackTrace method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

