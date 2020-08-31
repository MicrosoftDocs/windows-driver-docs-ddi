---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolTypeIdWide
title: IDebugSymbols3::GetSymbolTypeIdWide (dbgeng.h)
description: The GetSymbolTypeIdWide method returns the type ID and module of the specified symbol.
old-location: debugger\getsymboltypeidwide.htm
tech.root: debugger
ms.assetid: b68a5f89-1623-4cab-84bf-3cc6e4031d9b
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolTypeIdWide"]
ms.keywords: GetSymbolTypeIdWide, GetSymbolTypeIdWide method [Windows Debugging], GetSymbolTypeIdWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolTypeIdWide method, IDebugSymbols3.GetSymbolTypeIdWide, IDebugSymbols3::GetSymbolTypeIdWide, dbgeng/IDebugSymbols3::GetSymbolTypeIdWide, debugger.getsymboltypeidwide
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
 - IDebugSymbols3::GetSymbolTypeIdWide
 - dbgeng/IDebugSymbols3::GetSymbolTypeIdWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.GetSymbolTypeIdWide
---

# IDebugSymbols3::GetSymbolTypeIdWide


## -description

The <b>GetSymbolTypeIdWide</b>  method returns the type ID and module of the specified symbol.

## -parameters

### -param Symbol 

[in]
Specifies the expression whose type ID is requested.  See the Remarks section for details on the syntax of this expression.

### -param TypeId 

[out]
Receives the type ID.

### -param Module 

[out, optional]
Receives the base address of the module containing the symbol.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.

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
The method was successful

</td>
</tr>
</table>

## -remarks

The <i>Symbol</i> expression may contain structure fields, pointer dereferencing, and array dereferencing -- for example <b>my_struct.some_field[0]</b>.

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymboltypeid">GetSymbolTypeId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypeid">GetTypeId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

