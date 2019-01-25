---
UID: NF:dbgeng.IDebugSymbols3.GetScopeSymbolGroup2
title: IDebugSymbols3::GetScopeSymbolGroup2 (dbgeng.h)
description: The GetScopeSymbolGroup2 method returns a symbol group containing the symbols in the current target's scope.
old-location: debugger\getscopesymbolgroup2.htm
tech.root: debugger
ms.assetid: 2bc0cd81-db9b-4646-838b-0e66c0667202
ms.date: 05/03/2018
ms.keywords: GetScopeSymbolGroup2, GetScopeSymbolGroup2 method [Windows Debugging], GetScopeSymbolGroup2 method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetScopeSymbolGroup2 method, IDebugSymbols3.GetScopeSymbolGroup2, IDebugSymbols3::GetScopeSymbolGroup2, dbgeng/IDebugSymbols3::GetScopeSymbolGroup2, debugger.getscopesymbolgroup2
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
-	IDebugSymbols3.GetScopeSymbolGroup2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetScopeSymbolGroup2


## -description


The <b>GetScopeSymbolGroup2</b>  method returns a symbol group containing the symbols in the current target's scope.


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

Receives the symbol group interface object for the current scope.  For details on this interface, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a>



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



The <i>Update</i> parameter allows for efficient updates when stepping through code. Instead of creating and populating a new symbol group, the old symbol group can be updated.

For more information about scopes and symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550838">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

