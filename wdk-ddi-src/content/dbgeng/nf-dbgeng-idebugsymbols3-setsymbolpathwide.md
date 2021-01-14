---
UID: NF:dbgeng.IDebugSymbols3.SetSymbolPathWide
title: IDebugSymbols3::SetSymbolPathWide (dbgeng.h)
description: The SetSymbolPathWide method sets the symbol path.
old-location: debugger\setsymbolpathwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::SetSymbolPathWide"]
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetSymbolPathWide method, IDebugSymbols3.SetSymbolPathWide, IDebugSymbols3::SetSymbolPathWide, SetSymbolPathWide, SetSymbolPathWide method [Windows Debugging], SetSymbolPathWide method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetSymbolPathWide, debugger.setsymbolpathwide
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
 - IDebugSymbols3::SetSymbolPathWide
 - dbgeng/IDebugSymbols3::SetSymbolPathWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::SetSymbolPathWide
---

# IDebugSymbols3::SetSymbolPathWide


## -description

The <b>SetSymbolPathWide</b>  method sets the symbol path.

## -parameters

### -param Path 

[in]
Specifies the new symbol path.  This is a string that contains symbol path elements separated by semicolons (;).  Each symbol path element can specify either a directory or a symbol server.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about manipulating the symbol path, see <a href="/windows-hardware/drivers/debugger/using-symbols">Using Symbols</a>.  For an overview of the symbol path and its syntax, see <a href="/windows-hardware/drivers/debugger/symbol-path">Symbol Path</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendsymbolpath">AppendSymbolPath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolpath">GetSymbolPath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

