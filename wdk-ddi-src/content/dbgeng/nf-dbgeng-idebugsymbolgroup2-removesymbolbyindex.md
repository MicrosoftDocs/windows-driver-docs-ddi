---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByIndex
title: IDebugSymbolGroup2::RemoveSymbolByIndex (dbgeng.h)
description: The RemoveSymbolByIndex method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbyindex.htm
tech.root: debugger
ms.assetid: 1903d454-02d1-4528-9b8f-3c2eab8c6a6a
ms.date: 05/03/2018
ms.keywords: ComOther_d532b37e-11c9-4cff-a619-0b9dffef0af1.xml, IDebugSymbolGroup interface [Windows Debugging],RemoveSymbolByIndex method, IDebugSymbolGroup2 interface [Windows Debugging],RemoveSymbolByIndex method, IDebugSymbolGroup2.RemoveSymbolByIndex, IDebugSymbolGroup2::RemoveSymbolByIndex, IDebugSymbolGroup::RemoveSymbolByIndex, RemoveSymbolByIndex, RemoveSymbolByIndex method [Windows Debugging], RemoveSymbolByIndex method [Windows Debugging],IDebugSymbolGroup interface, RemoveSymbolByIndex method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::RemoveSymbolByIndex, dbgeng/IDebugSymbolGroup::RemoveSymbolByIndex, debugger.removesymbolbyindex
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbolGroup.RemoveSymbolByIndex"
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
- IDebugSymbolGroup.RemoveSymbolByIndex
- IDebugSymbolGroup2.RemoveSymbolByIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::RemoveSymbolByIndex


## -description


The <b>RemoveSymbolByIndex</b> method removes the specified symbol from a symbol group.


## -parameters




### -param Index [in]

The index of the symbol to remove. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


## -returns



<b>RemoveSymbolByIndex</b> might return one of the following values:

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
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



When a symbol is removed, the indexes of the symbols that remain in the symbol group might change.  

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-addsymbol">AddSymbol</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-removesymbolbyname">RemoveSymbolByName</a>
 

 

