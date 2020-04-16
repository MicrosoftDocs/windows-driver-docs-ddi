---
UID: NF:dbgeng.IDebugControl.GetStackTrace
title: IDebugControl::GetStackTrace (dbgeng.h)
description: The GetStackTrace method returns the frames at the top of the specified call stack.
old-location: debugger\getstacktrace.htm
tech.root: debugger
ms.assetid: 2d07e6a3-b560-4d9b-aece-0368d5929867
ms.date: 05/03/2018
keywords: ["IDebugControl::GetStackTrace"]
ms.keywords: GetStackTrace, GetStackTrace method [Windows Debugging], GetStackTrace method [Windows Debugging],IDebugControl interface, GetStackTrace method [Windows Debugging],IDebugControl2 interface, GetStackTrace method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetStackTrace method, IDebugControl.GetStackTrace, IDebugControl2 interface [Windows Debugging],GetStackTrace method, IDebugControl2::GetStackTrace, IDebugControl3 interface [Windows Debugging],GetStackTrace method, IDebugControl3::GetStackTrace, IDebugControl::GetStackTrace, IDebugControl_ef51127a-c022-4e3d-bb63-55553daea893.xml, dbgeng/IDebugControl2::GetStackTrace, dbgeng/IDebugControl3::GetStackTrace, dbgeng/IDebugControl::GetStackTrace, debugger.getstacktrace
f1_keywords:
 - "dbgeng/IDebugControl.GetStackTrace"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl.GetStackTrace
- IDebugControl2.GetStackTrace
- IDebugControl3.GetStackTrace
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



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



The stack trace returned to <i>Frames</i> can be printed using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputstacktrace">OutputStackTrace</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getcontextstacktrace">GetContextStackTrace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getframeoffset2">GetFrameOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset2">GetInstructionOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getstackoffset2">GetStackOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputstacktrace">OutputStackTrace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_stacktrace_routine">StackTrace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/k--kb--kc--kd--kp--kp--kv--display-stack-backtrace-">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
 

 

