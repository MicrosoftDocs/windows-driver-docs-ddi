---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolParameters
title: IDebugSymbolGroup2::GetSymbolParameters (dbgeng.h)
description: The GetSymbolParameters method returns the symbol parameters that describe the specified symbols in a symbol group.
old-location: debugger\getsymbolparameters.htm
tech.root: debugger
ms.assetid: e6390a7c-bbe1-47d7-9411-d710c4ab58a8
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::GetSymbolParameters"]
ms.keywords: ComOther_f81a6f5a-df93-4ae2-9694-88a25d6d67a8.xml, GetSymbolParameters, GetSymbolParameters method [Windows Debugging], GetSymbolParameters method [Windows Debugging],IDebugSymbolGroup interface, GetSymbolParameters method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup interface [Windows Debugging],GetSymbolParameters method, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolParameters method, IDebugSymbolGroup2.GetSymbolParameters, IDebugSymbolGroup2::GetSymbolParameters, IDebugSymbolGroup::GetSymbolParameters, dbgeng/IDebugSymbolGroup2::GetSymbolParameters, dbgeng/IDebugSymbolGroup::GetSymbolParameters, debugger.getsymbolparameters
f1_keywords:
 - "dbgeng/IDebugSymbolGroup.GetSymbolParameters"
 - "IDebugSymbolGroup.GetSymbolParameters"
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
- IDebugSymbolGroup.GetSymbolParameters
- IDebugSymbolGroup2.GetSymbolParameters
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::GetSymbolParameters


## -description


The <b>GetSymbolParameters</b> method returns the symbol parameters that describe the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">symbols</a> in a symbol group.


## -parameters




### -param Start 
[in]
The index in the symbol group of the first symbol whose parameters you want.  The index of a symbol is an identification number. This number ranges from zero through the number of symbols in the symbol group minus one.


### -param Count 
[in]
The number of symbol parameters that you want.


### -param Params 
[out]
The symbol parameters.  This array must hold at least <i>Count</i> elements.  For a description of these parameters, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_parameters">DEBUG_SYMBOL_PARAMETERS</a>.


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



For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_parameters">DEBUG_SYMBOL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

