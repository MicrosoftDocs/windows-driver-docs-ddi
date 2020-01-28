---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticSymbolWide
title: IDebugSymbols3::AddSyntheticSymbolWide (dbgeng.h)
description: The AddSyntheticSymbolWide method adds a synthetic symbol to a module in the current process.
old-location: debugger\addsyntheticsymbolwide.htm
tech.root: debugger
ms.assetid: 06d4d1f1-8d28-46cc-8c80-8a67cf4ae4c3
ms.date: 05/03/2018
ms.keywords: AddSyntheticSymbolWide, AddSyntheticSymbolWide method [Windows Debugging], AddSyntheticSymbolWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AddSyntheticSymbolWide method, IDebugSymbols3.AddSyntheticSymbolWide, IDebugSymbols3::AddSyntheticSymbolWide, dbgeng/IDebugSymbols3::AddSyntheticSymbolWide, debugger.addsyntheticsymbolwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.AddSyntheticSymbolWide"
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
- IDebugSymbols3.AddSyntheticSymbolWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AddSyntheticSymbolWide


## -description


The <b>AddSyntheticSymbolWide</b>  method adds a synthetic symbol to a module in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/c">current process</a>.


## -parameters




### -param Offset [in]

Specifies the location in the process's virtual address space of the synthetic symbol.


### -param Size [in]

Specifies the size in bytes of the synthetic symbol.


### -param Name [in]

Specifies the name of the synthetic symbol.


### -param Flags [in]

Set to DEBUG_ADDSYNTHSYM_DEFAULT.


### -param Id [out, optional]

Receives the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a> structure that identifies the synthetic symbol.  If <i>Id</i> is <b>NULL</b>, this information is not returned.


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



The location of the synthetic symbol must not be the same as the location of another symbol.

If the module containing a synthetic symbol is reloaded - for example, by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-reload">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-symbols">Synthetic Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticmodule">AddSyntheticModule</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-removesyntheticsymbol">RemoveSyntheticSymbol</a>
 

 

