---
UID: NF:dbgeng.IDebugSymbols3.OutputSymbolByOffset
title: IDebugSymbols3::OutputSymbolByOffset (dbgeng.h)
description: The OutputSymbolByOffset method looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.
old-location: debugger\outputsymbolbyoffset.htm
tech.root: debugger
ms.assetid: a9b3ac31-2001-45cc-a917-de687419b561
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::OutputSymbolByOffset"]
ms.keywords: IDebugSymbols3 interface [Windows Debugging],OutputSymbolByOffset method, IDebugSymbols3.OutputSymbolByOffset, IDebugSymbols3::OutputSymbolByOffset, IDebugSymbols_45f0a841-85cf-4be8-82bc-e962b5af2f5d.xml, OutputSymbolByOffset, OutputSymbolByOffset method [Windows Debugging], OutputSymbolByOffset method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::OutputSymbolByOffset, debugger.outputsymbolbyoffset
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
 - IDebugSymbols3::OutputSymbolByOffset
 - dbgeng/IDebugSymbols3::OutputSymbolByOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.OutputSymbolByOffset
---

# IDebugSymbols3::OutputSymbolByOffset


## -description

The <b>OutputSymbolByOffset</b> method looks up a symbol by address and prints the symbol name and other symbol information to the debugger console.

## -parameters

### -param OutputControl 

[in]
Specifies where to send the output. For possible values, see <a href="/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.

### -param Flags 

[in]
Specifies the flags used to determine what information is printed with the symbol.

The following flags can be present:

<table>
<tr>
<th>Bit-flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DEBUG_OUTSYM_FORCE_OFFSET

</td>
<td>
Include the location of the symbol.

</td>
</tr>
<tr>
<td>
DEBUG_OUTSYM_SOURCE_LINE

</td>
<td>
Include the file name and line number of the source file where the symbol is defined.

</td>
</tr>
<tr>
<td>
DEBUG_OUTSYM_ALLOW_DISPLACEMENT

</td>
<td>
Do not require an exact match for the symbols location.

This allows the <i>Offset</i> parameter to specify any address within the symbol's memory allocation - not just the base address.

</td>
</tr>
</table>

### -param Offset 

[in]
Specifies the location in the process's virtual address space of the symbol to be printed.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No symbol was found at the specified location.

</td>
</tr>
</table>

## -remarks

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnamebyoffset">GetNameByOffset</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>