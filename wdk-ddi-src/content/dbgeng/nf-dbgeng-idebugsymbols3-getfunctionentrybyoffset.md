---
UID: NF:dbgeng.IDebugSymbols3.GetFunctionEntryByOffset
title: IDebugSymbols3::GetFunctionEntryByOffset (dbgeng.h)
description: The GetFunctionEntryByOffset method returns the function entry information for a function.
old-location: debugger\getfunctionentrybyoffset.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetFunctionEntryByOffset"]
ms.keywords: GetFunctionEntryByOffset, GetFunctionEntryByOffset method [Windows Debugging], GetFunctionEntryByOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetFunctionEntryByOffset method, IDebugSymbols3.GetFunctionEntryByOffset, IDebugSymbols3::GetFunctionEntryByOffset, IDebugSymbols_2f48c855-76e5-421c-8890-9a96a0468783.xml, dbgeng/IDebugSymbols3::GetFunctionEntryByOffset, debugger.getfunctionentrybyoffset
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winnt.h
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
 - IDebugSymbols3::GetFunctionEntryByOffset
 - dbgeng/IDebugSymbols3::GetFunctionEntryByOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.GetFunctionEntryByOffset
---

# IDebugSymbols3::GetFunctionEntryByOffset


## -description

The <b>GetFunctionEntryByOffset</b> method returns the function entry information for a function.

## -parameters

### -param Offset 

[in]
Specifies a location in the current process's virtual address space of the function's implementation.  This is the value returned in the <i>Offset</i> parameter of <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a> and <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymboloffset">IDebugSymbolGroup::GetSymbolOffset</a>, and the value of the <b>Offset</b> field in the <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_entry">DEBUG_SYMBOL_ENTRY</a> structure.

### -param Flags 

[in]
Specifies a bit-flag which alters the behavior of this method.  If the bit DEBUG_GETFNENT_RAW_ENTRY_ONLY is not set, the engine will provide artificial entries for well known cases.  If this bit is set the artificial entries are not used.

### -param Buffer 

[out, optional]
Receives the function entry information.  If the effective processor is an x86, this is the FPO_DATA structure for the function.  For all other architectures, this is the IMAGE_FUNCTION_ENTRY structure for that architecture.

### -param BufferSize 

[in]
Specifies the size of the buffer <i>Buffer</i>.

### -param BufferNeeded 

[out, optional]
Specifies the size of the function entry information.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but the buffer was not large enough to hold the function entry information and so the information was truncated to fit.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No function entry information was found for the location <i>Offset</i>.

</td>
</tr>
</table>

## -remarks

The structures FPO_DATA and IMAGE_FUNCTION_ENTRY are documented in "Image Help Library" which is included in Debugging Tools For Windows in the DbgHelp.chm file. 

<div class="alert"><b>Note</b>  The functions in "Image Help Library" and "Debug Help Library", documented in DbgHelp.chm, should not be called by any extension or debugger engine application.</div>
<div> </div>
For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_entry">DEBUG_SYMBOL_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getnextsymbolmatch">GetNextSymbolMatch</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getsymboloffset">IDebugSymbolGroup::GetSymbolOffset</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
