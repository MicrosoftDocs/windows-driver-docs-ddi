---
UID: NF:dbgeng.IDebugSymbols3.RemoveSyntheticSymbol
title: IDebugSymbols3::RemoveSyntheticSymbol (dbgeng.h)
description: The RemoveSyntheticSymbol method removes a synthetic symbol from a module in the current process.
old-location: debugger\removesyntheticsymbol.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::RemoveSyntheticSymbol"]
ms.keywords: IDebugSymbols3 interface [Windows Debugging],RemoveSyntheticSymbol method, IDebugSymbols3.RemoveSyntheticSymbol, IDebugSymbols3::RemoveSyntheticSymbol, IDebugSymbols_dc1ccbc7-17e4-4424-8a3d-fbb7f16d3c3b.xml, RemoveSyntheticSymbol, RemoveSyntheticSymbol method [Windows Debugging], RemoveSyntheticSymbol method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::RemoveSyntheticSymbol, debugger.removesyntheticsymbol
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
 - IDebugSymbols3::RemoveSyntheticSymbol
 - dbgeng/IDebugSymbols3::RemoveSyntheticSymbol
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.RemoveSyntheticSymbol
---

# IDebugSymbols3::RemoveSyntheticSymbol


## -description

The <b>RemoveSyntheticSymbol</b> method removes a synthetic symbol from a module in the current process.

## -parameters

### -param Id 

[in]
Specifies the synthetic symbol to remove.  This must be the same value returned in the <i>Id</i> parameter of <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticsymbol">AddSyntheticSymbol</a>.  See <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a> for details about the type of this parameter.

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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
No synthetic symbol was found at the specified location.  This is returned if a synthetic symbol at this location was previously removed or discarded.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

If the module containing a synthetic symbol is reloaded - for example, by calling <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-reload">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see Synthetic Symbols.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-addsyntheticsymbol">AddSyntheticSymbol</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-removesyntheticmodule">RemoveSyntheticModule</a>
