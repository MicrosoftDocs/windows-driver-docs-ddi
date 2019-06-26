---
UID: NF:dbgeng.IDebugAdvanced2.SetThreadContext
title: IDebugAdvanced2::SetThreadContext (dbgeng.h)
description: The SetThreadContext method sets the current thread context.
old-location: debugger\setthreadcontext.htm
tech.root: debugger
ms.assetid: eaaaa9d7-ba6d-4379-b721-74c92375ea05
ms.date: 05/03/2018
ms.keywords: IDebugAdvanced interface [Windows Debugging],SetThreadContext method, IDebugAdvanced2 interface [Windows Debugging],SetThreadContext method, IDebugAdvanced2.SetThreadContext, IDebugAdvanced2::SetThreadContext, IDebugAdvanced3 interface [Windows Debugging],SetThreadContext method, IDebugAdvanced3::SetThreadContext, IDebugAdvanced::SetThreadContext, IDebugAdvanced_08e9f1e1-7af3-4cdf-9550-7d22fa5a59da.xml, SetThreadContext, SetThreadContext method [Windows Debugging], SetThreadContext method [Windows Debugging],IDebugAdvanced interface, SetThreadContext method [Windows Debugging],IDebugAdvanced2 interface, SetThreadContext method [Windows Debugging],IDebugAdvanced3 interface, dbgeng/IDebugAdvanced2::SetThreadContext, dbgeng/IDebugAdvanced3::SetThreadContext, dbgeng/IDebugAdvanced::SetThreadContext, debugger.setthreadcontext
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugAdvanced.SetThreadContext
- IDebugAdvanced2.SetThreadContext
- IDebugAdvanced3.SetThreadContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugAdvanced2::SetThreadContext


## -description


The <b>SetThreadContext</b> method sets the current <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">thread context</a>.


## -parameters




### -param Context [in]

Specifies the thread context. The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>Context</i> must be large enough to hold this structure.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugadvanced3-getthreadcontext">GetThreadContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugadvanced">IDebugAdvanced</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugadvanced2">IDebugAdvanced2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugadvanced3">IDebugAdvanced3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setscope">SetScope</a>
 

 

