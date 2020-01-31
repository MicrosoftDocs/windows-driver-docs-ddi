---
UID: NF:dbgeng.IDebugAdvanced3.GetThreadContext
title: IDebugAdvanced3::GetThreadContext (dbgeng.h)
description: The GetThreadContext method returns the current thread context.
old-location: debugger\getthreadcontext.htm
tech.root: debugger
ms.assetid: 6fe12f3b-b241-42e4-b35d-c8a485a5cfa8
ms.date: 05/03/2018
ms.keywords: GetThreadContext, GetThreadContext method [Windows Debugging], GetThreadContext method [Windows Debugging],IDebugAdvanced interface, GetThreadContext method [Windows Debugging],IDebugAdvanced2 interface, GetThreadContext method [Windows Debugging],IDebugAdvanced3 interface, IDebugAdvanced interface [Windows Debugging],GetThreadContext method, IDebugAdvanced2 interface [Windows Debugging],GetThreadContext method, IDebugAdvanced2::GetThreadContext, IDebugAdvanced3 interface [Windows Debugging],GetThreadContext method, IDebugAdvanced3.GetThreadContext, IDebugAdvanced3::GetThreadContext, IDebugAdvanced::GetThreadContext, IDebugAdvanced_1a044a89-612f-4a3c-b3cd-0a715ae6af92.xml, dbgeng/IDebugAdvanced2::GetThreadContext, dbgeng/IDebugAdvanced3::GetThreadContext, dbgeng/IDebugAdvanced::GetThreadContext, debugger.getthreadcontext
f1_keywords:
 - "dbgeng/IDebugAdvanced.GetThreadContext"
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
- IDebugAdvanced.GetThreadContext
- IDebugAdvanced2.GetThreadContext
- IDebugAdvanced3.GetThreadContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugAdvanced3::GetThreadContext


## -description


The <b>GetThreadContext</b> method returns the current <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">thread context</a>.


## -parameters




### -param Context [out]

Receives the current thread context. The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>Context</i> must be large enough to hold this structure.


### -param ContextSize [in]

Specifies the size of the buffer <i>Context</i>.


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



For more information about the thread context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

<div class="alert"><b>Note</b>    The CONTEXT structure varies with operating system and platform.  Care should be taken when using the CONTEXT structure.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getscope">GetScope</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugadvanced">IDebugAdvanced</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugadvanced2">IDebugAdvanced2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugadvanced3">IDebugAdvanced3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-setthreadcontext">SetThreadContext</a>
 

 

