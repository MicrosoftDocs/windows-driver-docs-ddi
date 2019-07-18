---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntriesByLineWide
title: IDebugSymbols3::GetSourceEntriesByLineWide (dbgeng.h)
description: The GetSourceEntriesByLineWide method queries symbol information and returns locations in the target's memory that correspond to lines in a source file.
old-location: debugger\getsourceentriesbylinewide.htm
tech.root: debugger
ms.assetid: c0c61c6a-35fe-410a-b3e8-70d33557bb9b
ms.date: 05/03/2018
ms.keywords: GetSourceEntriesByLineWide, GetSourceEntriesByLineWide method [Windows Debugging], GetSourceEntriesByLineWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntriesByLineWide method, IDebugSymbols3.GetSourceEntriesByLineWide, IDebugSymbols3::GetSourceEntriesByLineWide, dbgeng/IDebugSymbols3::GetSourceEntriesByLineWide, debugger.getsourceentriesbylinewide
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetSourceEntriesByLineWide"
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
- IDebugSymbols3.GetSourceEntriesByLineWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSourceEntriesByLineWide


## -description


The <b>GetSourceEntriesByLineWide</b>  method queries symbol information and returns locations in the target's memory that correspond to lines in a source file.


## -parameters




### -param Line [in]

Specifies the line in the source file for which to query.  The number for the first line is <b>1</b>.


### -param File [in]

Specifies the source file.  The symbols for each module in the target are queried for this file.


### -param Flags [in]

Specifies bit flags that control the behavior of this method.  <i>Flags</i> can be any combination of values from the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_GSEL_NO_SYMBOL_LOADS

</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> will only search for the file among the modules whose symbols have already been loaded.  Symbols for the other modules will not be loaded.

If this option is not set, the debugger engine will load the symbols for all modules until it finds the file specified in <i>File</i>.

</td>
</tr>
<tr>
<td>
DEBUG_GSEL_ALLOW_LOWER

</td>
<td>
Include all the lines in <i>File</i> before <i>Line</i> in the result.

</td>
</tr>
<tr>
<td>
DEBUG_GSEL_ALLOW_HIGHER

</td>
<td>
Include all the lines in <i>File</i> after <i>Line</i> in the result.

</td>
</tr>
<tr>
<td>
DEBUG_GSEL_NEAREST_ONLY

</td>
<td>
Only return at most one result.  If DEBUG_GSEL_ALLOW_LOWER or DEBUG_GSEL_ALLOW_HIGHER are set, the returned result will be for a line close to <i>Line</i> but cannot be <i>Line</i> if there is no symbol information for that line.

</td>
</tr>
</table>
 

To use the default set of flags, set <i>Flags</i> to DEBUG_GSEL_DEFAULT.  This has all the flags in the previous table turned off.


### -param Entries [out, optional]

Receives the locations in the target's memory that correspond to the source lines queried for.  Each entry in this array is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> and contains the source line number along with a location in the target's memory.


### -param EntriesCount [in]

Specifies the number of entries in the <i>Entries</i> array.


### -param EntriesAvail






#### - EntriesAvailable [out, optional]

Receives the number of locations that match the query found in the target's memory.


## -returns



These methods can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful.  However, the <i>Entries</i> array was not large enough to hold all the results that matched the query and the extra results were discarded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The query yielded no results.  This includes the case where the symbol information was not available for the specified file.

</td>
</tr>
</table>
 




## -remarks



These methods can be used by debugger applications to fetch locations in the target's memory for setting breakpoints or matching source code with disassembled instructions.  For example, setting the flags DEBUG_GSEL_ALLOW_HIGHER and DEBUG_GSEL_NEAREST_ONLY will return the target's memory location for the first piece of code starting at the specified line.

For more information about source files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourcefilelineoffsets">GetSourceFileLineOffsets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

