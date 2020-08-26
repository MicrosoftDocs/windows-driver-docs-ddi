---
UID: NF:dbgeng.IDebugSymbols3.GetCurrentScopeFrameIndex
title: IDebugSymbols3::GetCurrentScopeFrameIndex (dbgeng.h)
description: The GetCurrentScopeFrameIndex method returns the index of the current stack frame in the call stack.
old-location: debugger\getcurrentscopeframeindex.htm
tech.root: debugger
ms.assetid: 735934c5-70c4-4bd5-a5ff-e2d313191b69
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetCurrentScopeFrameIndex"]
ms.keywords: GetCurrentScopeFrameIndex, GetCurrentScopeFrameIndex method [Windows Debugging], GetCurrentScopeFrameIndex method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetCurrentScopeFrameIndex method, IDebugSymbols3.GetCurrentScopeFrameIndex, IDebugSymbols3::GetCurrentScopeFrameIndex, IDebugSymbols_293a8676-cbda-4b24-a6e0-d80f365cb283.xml, dbgeng/IDebugSymbols3::GetCurrentScopeFrameIndex, debugger.getcurrentscopeframeindex
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetCurrentScopeFrameIndex"
 - "IDebugSymbols3.GetCurrentScopeFrameIndex"
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
- IDebugSymbols3.GetCurrentScopeFrameIndex
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetCurrentScopeFrameIndex


## -description


The <b>GetCurrentScopeFrameIndex</b> method returns the index of the current stack frame in the call stack.


## -parameters




### -param Index 
[out]
Receives the index of the stack frame corresponding to the current scope.  The index counts the number of frames from the top of the call stack.  The frame at the top of the stack, representing the current call, has index zero.


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



If the current scope was set using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setscope">SetScope</a>, <i>Index</i> receives the value of the <b>FrameNumber</b> member of the DEBUG_STACK_TRACE structure passed to the <i>ScopeFrame</i> parameter of <b>SetScope</b>.

For more information about scopes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-frame--set-local-context-">.frame (Set Local Context)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getscope">GetScope</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setscopeframebyindex">SetScopeFrameByIndex</a>
 

 

