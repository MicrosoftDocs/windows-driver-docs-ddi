---
UID: NF:dbgeng.IDebugSymbolGroup2.WriteSymbol
title: IDebugSymbolGroup2::WriteSymbol (dbgeng.h)
description: The WriteSymbol methods set the value of the specified symbol.
old-location: debugger\writesymbol.htm
tech.root: debugger
ms.assetid: c0c23778-767a-4304-9ecf-c76337261e27
ms.date: 05/03/2018
ms.keywords: ComOther_3b8938be-b82e-404c-b80f-36e1ceedc353.xml, IDebugSymbolGroup interface [Windows Debugging],WriteSymbol method, IDebugSymbolGroup2 interface [Windows Debugging],WriteSymbol method, IDebugSymbolGroup2.WriteSymbol, IDebugSymbolGroup2::WriteSymbol, IDebugSymbolGroup::WriteSymbol, WriteSymbol, WriteSymbol method [Windows Debugging], WriteSymbol method [Windows Debugging],IDebugSymbolGroup interface, WriteSymbol method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::WriteSymbol, dbgeng/IDebugSymbolGroup::WriteSymbol, debugger.writesymbol
f1_keywords:
 - "dbgeng/IDebugSymbolGroup.WriteSymbol"
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
- IDebugSymbolGroup.WriteSymbol
- IDebugSymbolGroup2.WriteSymbol
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::WriteSymbol


## -description


The <b>WriteSymbol</b>  methods set the value of the specified symbol.


## -parameters




### -param Index [in]

The index of the symbol whose value will be changed. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Value [in]

A C++ expression that is evaluated to give the symbol's new value.


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
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



The <b>WriteSymbol</b>  method can change symbols only if the symbols are stored in a register or memory location that the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> knowns and if they have not had their type changed to an extension by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-outputastype">OutputAsType</a> method.  

For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymbolvaluetext">GetSymbolValueText</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

