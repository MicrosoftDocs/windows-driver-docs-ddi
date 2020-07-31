---
UID: NF:dbgeng.IDebugSymbolGroup.ExpandSymbol
title: IDebugSymbolGroup::ExpandSymbol (dbgeng.h)
description: The ExpandSymbol method adds or removes the children of a symbol from a symbol group.
old-location: debugger\expandsymbol.htm
tech.root: debugger
ms.assetid: 314fdeea-10be-4cb3-8bd7-9b1b4b12e534
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup::ExpandSymbol"]
ms.keywords: ComOther_894f45d2-9f7b-4d8d-85e3-9240d020ebbe.xml, ExpandSymbol, ExpandSymbol method [Windows Debugging], ExpandSymbol method [Windows Debugging],IDebugSymbolGroup interface, ExpandSymbol method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup interface [Windows Debugging],ExpandSymbol method, IDebugSymbolGroup.ExpandSymbol, IDebugSymbolGroup2 interface [Windows Debugging],ExpandSymbol method, IDebugSymbolGroup2::ExpandSymbol, IDebugSymbolGroup::ExpandSymbol, dbgeng/IDebugSymbolGroup2::ExpandSymbol, dbgeng/IDebugSymbolGroup::ExpandSymbol, debugger.expandsymbol
f1_keywords:
 - "dbgeng/IDebugSymbolGroup.ExpandSymbol"
 - "IDebugSymbolGroup.ExpandSymbol"
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
- IDebugSymbolGroup.ExpandSymbol
- IDebugSymbolGroup2.ExpandSymbol
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup::ExpandSymbol


## -description


The <b>ExpandSymbol</b> method adds or removes the children of a symbol from a symbol group.


## -parameters




### -param Index [in]

The index of the symbol whose children will be added or removed.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Expand [in]

A Boolean value that specifies whether to add or remove the symbols children from the symbol group.  If <i>Expand</i> is true, the children are added.  If <i>Expand</i> is false, the children are removed.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The symbol has no children to add.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The depth of the symbol is DEBUG_SYMBOL_EXPANSION_LEVEL_MASK,  which is the maximum depth. This depth prevented the specified symbol's children from being added to this symbol group.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

