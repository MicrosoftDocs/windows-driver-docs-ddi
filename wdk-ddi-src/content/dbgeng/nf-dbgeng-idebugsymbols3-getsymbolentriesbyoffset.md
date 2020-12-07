---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntriesByOffset
title: IDebugSymbols3::GetSymbolEntriesByOffset (dbgeng.h)
description: The GetSymbolEntriesByOffset method returns the symbols which are located at a specified address.
old-location: debugger\getsymbolentriesbyoffset.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSymbolEntriesByOffset"]
ms.keywords: GetSymbolEntriesByOffset, GetSymbolEntriesByOffset method [Windows Debugging], GetSymbolEntriesByOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolEntriesByOffset method, IDebugSymbols3.GetSymbolEntriesByOffset, IDebugSymbols3::GetSymbolEntriesByOffset, IDebugSymbols_dba4bc10-a8a8-476d-b668-652c24743ea5.xml, dbgeng/IDebugSymbols3::GetSymbolEntriesByOffset, debugger.getsymbolentriesbyoffset
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
 - IDebugSymbols3::GetSymbolEntriesByOffset
 - dbgeng/IDebugSymbols3::GetSymbolEntriesByOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.GetSymbolEntriesByOffset
---

# IDebugSymbols3::GetSymbolEntriesByOffset


## -description

The <b>GetSymbolEntriesByOffset</b> method returns the <a href="/windows-hardware/drivers/debugger/symbols4">symbols</a> which are located at a specified address.

## -parameters

### -param Offset 

[in]
Specifies a location in the process's memory address space within the desired symbol's range.  Not all symbols have a known range, so, for best results, use the base address of the symbol.

### -param Flags 

[in]
Set to zero.

### -param Ids 

[out, optional]
Receives the symbols.  This is an array of <i>IdsCount</i> entries of type <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_module_and_id">DEBUG_MODULE_AND_ID</a>.  If <i>Ids</i> is <b>NULL</b>, this information is not returned.

### -param Displacements 

[out, optional]
Receives the differences between the base addresses of the found symbols and the given address according to the symbol's range.

### -param IdsCount 

[in]
Specifies the number of entries that the arrays <i>Ids</i> and <i>Displacements</i> can hold.

### -param Entries 

[out, optional]
Receives the number of symbols located at <i>Offset</i>.  If <i>Entries</i> is <b>NULL</b>, this information is not returned.

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
</table>

## -remarks

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymbolentriesbyname">GetSymbolEntriesByName</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
