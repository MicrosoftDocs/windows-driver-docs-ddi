---
UID: NF:dbgeng.IDebugSymbols3.SetScopeFrameByIndex
title: IDebugSymbols3::SetScopeFrameByIndex
author: windows-driver-content
description: The SetScopeFrameByIndex method sets the current scope to the scope of one of the frames on the call stack.
old-location: debugger\setscopeframebyindex.htm
tech.root: debugger
ms.assetid: 7d5105e3-99c6-4800-88a4-af80a61c253e
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetScopeFrameByIndex method, IDebugSymbols3.SetScopeFrameByIndex, IDebugSymbols3::SetScopeFrameByIndex, IDebugSymbols_451c9980-0e6c-4661-bdb6-396c45cc57dd.xml, SetScopeFrameByIndex, SetScopeFrameByIndex method [Windows Debugging], SetScopeFrameByIndex method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetScopeFrameByIndex, debugger.setscopeframebyindex
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
-	IDebugSymbols3.SetScopeFrameByIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::SetScopeFrameByIndex


## -description


The <b>SetScopeFrameByIndex</b> method sets the current scope to the scope of one of the frames on the call stack.


## -parameters




### -param Index [in]

Specifies the index of the stack frame from which to set the scope.  The index counts the number of frames from the top of the call stack.  The frame at the top of the stack, representing the current call, has index zero.


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



When an event occurs and the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> breaks into a target, the scope is set to the current function call (the function that was executing when the event occurred).  Calling this method with <i>Index</i> set to one will change the current scope to the caller of the current function; with <i>Index</i> set to two, the scope is changed to the caller's caller, and so on.

For more information about scopes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563155">.frame (Set Local Context)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545862">GetCurrentScopeFrameIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556778">SetScopeFromStoredEvent</a>
 

 

