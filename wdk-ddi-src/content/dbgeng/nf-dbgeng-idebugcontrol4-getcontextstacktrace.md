---
UID: NF:dbgeng.IDebugControl4.GetContextStackTrace
title: IDebugControl4::GetContextStackTrace method
author: windows-driver-content
description: The GetContextStackTrace method returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.
old-location: debugger\getcontextstacktrace.htm
old-project: debugger
ms.assetid: 8d7a461e-46bf-4556-b13c-805bb5af572e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetContextStackTrace method [Windows Debugging], GetContextStackTrace method [Windows Debugging], IDebugControl4 interface, GetContextStackTrace,IDebugControl4.GetContextStackTrace, IDebugControl4, IDebugControl4 interface [Windows Debugging], GetContextStackTrace method, IDebugControl4::GetContextStackTrace, IDebugControl_ae12ec1a-8839-49cc-8082-c328a570188b.xml, dbgeng/IDebugControl4::GetContextStackTrace, debugger.getcontextstacktrace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	IDebugControl4.GetContextStackTrace
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::GetContextStackTrace method


## -description


The <b>GetContextStackTrace</b> method returns the frames at the top of the call stack, starting with an arbitrary <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a> and returning the reconstructed register context for each stack frame.


## -syntax


````
HRESULT GetContextStackTrace(
  [in, optional]  PVOID              StartContext,
  [in]            ULONG              StartContextSize,
  [out, optional] PDEBUG_STACK_FRAME Frames,
  [in]            ULONG              FramesSize,
  [out, optional] PVOID              FrameContexts,
  [in]            ULONG              FrameContextsSize,
  [in]            ULONG              FrameContextsEntrySize,
  [out, optional] PULONG             FramesFilled
);
````


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
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



The stack trace returned to <i>Frames</i> and <i>FrameContexts</i> can be printed using <a href="https://msdn.microsoft.com/library/windows/hardware/ff553203">OutputContextStackTrace</a>.

It is common for stack unwinds to restore only a subset of the registers.  For example, stack unwinds will not always restore the volatile register state because the volatile registers are scratch registers and code does not need to preserve them.  Registers that are not restored on unwind are left as the last value restored, so care should be taken when using the register state that might not be restored by an unwind.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553203">OutputContextStackTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548425">GetStackTrace</a>



<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetContextStackTrace method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

