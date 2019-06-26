---
UID: NF:dbgeng.IDebugSymbols3.SetScopeFromStoredEvent
title: IDebugSymbols3::SetScopeFromStoredEvent (dbgeng.h)
description: The SetScopeFromStoredEvent method sets the current scope to the scope of the stored event.
old-location: debugger\setscopefromstoredevent.htm
tech.root: debugger
ms.assetid: 34c50e32-37c8-4e6a-a666-fce8880cb000
ms.date: 05/03/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetScopeFromStoredEvent method, IDebugSymbols3.SetScopeFromStoredEvent, IDebugSymbols3::SetScopeFromStoredEvent, IDebugSymbols_710b59d8-620b-479f-bfeb-dd1196cd2dbc.xml, SetScopeFromStoredEvent, SetScopeFromStoredEvent method [Windows Debugging], SetScopeFromStoredEvent method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetScopeFromStoredEvent, debugger.setscopefromstoredevent
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
- Dbgeng.h
api_name:
- IDebugSymbols3.SetScopeFromStoredEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::SetScopeFromStoredEvent


## -description


The <b>SetScopeFromStoredEvent</b> method sets the current scope to the scope of the stored event.


## -parameters






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
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



Currently only user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/user-mode-dump-files#minidumps">Minidumps</a> can contain a stored event.

The new scope is printed to the debugger console.

For more information about scopes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-ecxr--display-exception-context-record-">.ecxr (Display Exception Context Record)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol4-getstoredeventinformation">GetStoredEventInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setscope">SetScope</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-setscopeframebyindex">SetScopeFrameByIndex</a>
 

 

