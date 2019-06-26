---
UID: NF:dbgeng.IDebugSymbols.GetScopeSymbolGroup
title: IDebugSymbols::GetScopeSymbolGroup (dbgeng.h)
description: The GetScopeSymbolGroup method returns a symbol group containing the symbols in the current target's scope.
old-location: debugger\getscopesymbolgroup.htm
tech.root: debugger
ms.assetid: 002af3f1-4879-40e9-a5c6-bf62a3b26e02
ms.date: 05/03/2018
ms.keywords: GetScopeSymbolGroup, GetScopeSymbolGroup method [Windows Debugging], GetScopeSymbolGroup method [Windows Debugging],IDebugSymbols interface, GetScopeSymbolGroup method [Windows Debugging],IDebugSymbols2 interface, GetScopeSymbolGroup method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetScopeSymbolGroup method, IDebugSymbols.GetScopeSymbolGroup, IDebugSymbols2 interface [Windows Debugging],GetScopeSymbolGroup method, IDebugSymbols2::GetScopeSymbolGroup, IDebugSymbols3 interface [Windows Debugging],GetScopeSymbolGroup method, IDebugSymbols3::GetScopeSymbolGroup, IDebugSymbols::GetScopeSymbolGroup, IDebugSymbols_a51f6be3-09dc-48a4-ae45-149fea6bfb1b.xml, dbgeng/IDebugSymbols2::GetScopeSymbolGroup, dbgeng/IDebugSymbols3::GetScopeSymbolGroup, dbgeng/IDebugSymbols::GetScopeSymbolGroup, debugger.getscopesymbolgroup
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
- IDebugSymbols.GetScopeSymbolGroup
- IDebugSymbols2.GetScopeSymbolGroup
- IDebugSymbols3.GetScopeSymbolGroup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::GetScopeSymbolGroup


## -description


The <b>GetScopeSymbolGroup</b>  method returns a symbol group containing the symbols in the current target's scope.


## -parameters




### -param Flags [in]

Specifies a bit-set used to determine which symbols to include in the symbol group.  To include all symbols, set <i>Flags</i> to DEBUG_SCOPE_GROUP_ALL.  The following bit-flags determine which symbols are included.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_SCOPE_GROUP_ARGUMENTS

</td>
<td>
Include the function arguments for the current scope.

</td>
</tr>
<tr>
<td>
DEBUG_SCOPE_GROUP_LOCALS

</td>
<td>
Include the local variables for the current scope.

</td>
</tr>
</table>
 


### -param Update [in, optional]

Specifies a previously created symbol group that will be updated to reflect the current scope.  If <i>Update</i> is <b>NULL</b>, a new symbol group interface object is created.


### -param Symbols [out]

Receives the symbol group interface object for the current scope.  For details on this interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



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



The <i>Update</i> parameter allows for efficient updates when stepping through code. Instead of creating and populating a new symbol group, the old symbol group can be updated.

For more information about scopes and symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getscope">GetScope</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

