---
UID: NF:dbgeng.IDebugAdvanced3.GetThreadContext
title: IDebugAdvanced3::GetThreadContext method
author: windows-driver-content
description: The GetThreadContext method returns the current thread context.
old-location: debugger\getthreadcontext.htm
old-project: debugger
ms.assetid: 6fe12f3b-b241-42e4-b35d-c8a485a5cfa8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetThreadContext method [Windows Debugging], GetThreadContext method [Windows Debugging], IDebugAdvanced interface, GetThreadContext method [Windows Debugging], IDebugAdvanced2 interface, GetThreadContext method [Windows Debugging], IDebugAdvanced3 interface, GetThreadContext,IDebugAdvanced3.GetThreadContext, IDebugAdvanced interface [Windows Debugging], GetThreadContext method, IDebugAdvanced2 interface [Windows Debugging], GetThreadContext method, IDebugAdvanced2::GetThreadContext, IDebugAdvanced3, IDebugAdvanced3 interface [Windows Debugging], GetThreadContext method, IDebugAdvanced3::GetThreadContext, IDebugAdvanced::GetThreadContext, IDebugAdvanced_1a044a89-612f-4a3c-b3cd-0a715ae6af92.xml, dbgeng/IDebugAdvanced2::GetThreadContext, dbgeng/IDebugAdvanced3::GetThreadContext, dbgeng/IDebugAdvanced::GetThreadContext, debugger.getthreadcontext
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugAdvanced.GetThreadContext
-	IDebugAdvanced2.GetThreadContext
-	IDebugAdvanced3.GetThreadContext
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugAdvanced3::GetThreadContext method


## -description


The <b>GetThreadContext</b> method returns the current <a href="https://msdn.microsoft.com/f14b6361-9962-4fa3-bb1a-dfde066754b9">thread context</a>.


## -syntax


````
HRESULT GetThreadContext(
  [out] PVOID Context,
  [in]  ULONG ContextSize
);
````


## -parameters




### -param Context [out]

Receives the current thread context. The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>Context</i> must be large enough to hold this structure.


### -param ContextSize [in]

Specifies the size of the buffer <i>Context</i>.


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
 




## -remarks



For more information about the thread context, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

<div class="alert"><b>Note</b>    The CONTEXT structure varies with operating system and platform.  Care should be taken when using the CONTEXT structure.</div>
<div> </div>



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugadvanced.md">IDebugAdvanced</a>



<a href="..\dbgeng\nn-dbgeng-idebugadvanced2.md">IDebugAdvanced2</a>



<a href="..\dbgeng\nn-dbgeng-idebugadvanced3.md">IDebugAdvanced3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556829">SetThreadContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced::GetThreadContext method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

