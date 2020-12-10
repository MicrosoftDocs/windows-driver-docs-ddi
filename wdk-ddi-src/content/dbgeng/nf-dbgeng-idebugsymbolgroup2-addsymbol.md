---
UID: NF:dbgeng.IDebugSymbolGroup2.AddSymbol
title: IDebugSymbolGroup2::AddSymbol (dbgeng.h)
description: The AddSymbol method adds a symbol to a symbol group.
old-location: debugger\addsymbol.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::AddSymbol"]
ms.keywords: AddSymbol, AddSymbol method [Windows Debugging], AddSymbol method [Windows Debugging],IDebugSymbolGroup interface, AddSymbol method [Windows Debugging],IDebugSymbolGroup2 interface, ComOther_936851e7-6a8b-4b42-b339-9c8aa096d684.xml, IDebugSymbolGroup interface [Windows Debugging],AddSymbol method, IDebugSymbolGroup2 interface [Windows Debugging],AddSymbol method, IDebugSymbolGroup2.AddSymbol, IDebugSymbolGroup2::AddSymbol, IDebugSymbolGroup::AddSymbol, dbgeng/IDebugSymbolGroup2::AddSymbol, dbgeng/IDebugSymbolGroup::AddSymbol, debugger.addsymbol
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSymbolGroup2::AddSymbol
 - dbgeng/IDebugSymbolGroup2::AddSymbol
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbolGroup.AddSymbol
 - IDebugSymbolGroup2.AddSymbol
---

# IDebugSymbolGroup2::AddSymbol


## -description

The <b>AddSymbol</b>  method adds a symbol to a <a href="/windows-hardware/drivers/debugger/s">symbol group</a>.

## -parameters

### -param Name 

[in]
The symbol's name.  <i>Name</i> is examined as an expression to determine the symbol's <a href="/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-get_type">type</a>.  This expression can include pointer, array, and structure dereferencing (for example, <b>*my_pointer</b>, <b>my_array[1]</b>, or <b>my_struct.some_field</b>).

### -param Index 

[in, out]
The index of the entry in the symbol group.  When you are calling <b>AddSymbol</b> or <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbolwide">AddSymbolWide</a>, <i>Index</i> should point to the index of the symbol that you want. Or, if <i>Index</i> points to DEBUG_ANY_ID, the symbol is appended to the end of the list.   

When this method returns, <i>Index</i> points to the actual index of the symbol.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

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
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

The symbol name in <i>Name</i> is evaluated by the <a href="/windows-hardware/drivers/debugger/c---numbers-and-operators">C++ expression evaluator</a> and can contain any C++ expression (for example, <b>x+y</b>).

If the index that you want is less than the size of the symbol group, the new symbol is added at the desired index.  If the desired index is larger than the size of the symbol group, the new symbol is added to the end of the list (as in the case of DEBUG_ANY_ID).

For more information about symbol groups, see <a href="/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyindex">RemoveSymbolByIndex</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyname">RemoveSymbolByName</a>
