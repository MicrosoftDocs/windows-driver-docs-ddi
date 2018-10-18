---
UID: NF:dbgeng.IDebugControl.GetStackTrace
title: IDebugControl::GetStackTrace
author: windows-driver-content
description: The GetStackTrace method returns the frames at the top of the specified call stack.
old-location: debugger\getstacktrace.htm
tech.root: debugger
ms.assetid: 2d07e6a3-b560-4d9b-aece-0368d5929867
ms.date: 5/3/2018
ms.keywords: GetStackTrace, GetStackTrace method [Windows Debugging], GetStackTrace method [Windows Debugging],IDebugControl interface, GetStackTrace method [Windows Debugging],IDebugControl2 interface, GetStackTrace method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetStackTrace method, IDebugControl.GetStackTrace, IDebugControl2 interface [Windows Debugging],GetStackTrace method, IDebugControl2::GetStackTrace, IDebugControl3 interface [Windows Debugging],GetStackTrace method, IDebugControl3::GetStackTrace, IDebugControl::GetStackTrace, IDebugControl_ef51127a-c022-4e3d-bb63-55553daea893.xml, dbgeng/IDebugControl2::GetStackTrace, dbgeng/IDebugControl3::GetStackTrace, dbgeng/IDebugControl::GetStackTrace, debugger.getstacktrace
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
req.lib: 
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
-	IDebugControl.GetStackTrace
-	IDebugControl2.GetStackTrace
-	IDebugControl3.GetStackTrace
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetStackTrace


## -description


The <b>GetStackTrace</b> method returns the frames at the top of the specified call stack.


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



The stack trace returned to <i>Frames</i> can be printed using <a href="https://msdn.microsoft.com/library/windows/hardware/ff553252">OutputStackTrace</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545748">GetContextStackTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553252">OutputStackTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558794">StackTrace</a>



<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
 

 

