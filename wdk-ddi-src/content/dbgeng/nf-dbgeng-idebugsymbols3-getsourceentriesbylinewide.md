---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntriesByLineWide
title: IDebugSymbols3::GetSourceEntriesByLineWide method
author: windows-driver-content
description: The GetSourceEntriesByLineWide method queries symbol information and returns locations in the target's memory that correspond to lines in a source file.
old-location: debugger\getsourceentriesbylinewide.htm
old-project: debugger
ms.assetid: c0c61c6a-35fe-410a-b3e8-70d33557bb9b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 3, :, B, D, E, G, GetSourceEntriesByLineWide method [Windows Debugging], GetSourceEntriesByLineWide method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntriesByLineWide,IDebugSymbols3.GetSourceEntriesByLineWide, I, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntriesByLineWide method, IDebugSymbols3::GetSourceEntriesByLineWide, L, S, W, b, c, d, dbgeng/IDebugSymbols3::GetSourceEntriesByLineWide, debugger.getsourceentriesbylinewide, e, g, i, l, m, n, o, r, s, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols3.GetSourceEntriesByLineWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourceEntriesByLineWide method


## -description


The <b>GetSourceEntriesByLineWide</b>  method queries symbol information and returns locations in the target's memory that correspond to lines in a source file.


## -syntax


````
HRESULT GetSourceEntriesByLineWide(
  [in]            ULONG                      Line,
  [in]            PCWSTR                     File,
  [in]            ULONG                      Flags,
  [out, optional] PDEBUG_SYMBOL_SOURCE_ENTRY Entries,
  [in]            ULONG                      EntriesCount,
  [out, optional] PULONG                     EntriesAvailable
);
````


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
The <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> will only search for the file among the modules whose symbols have already been loaded.  Symbols for the other modules will not be loaded.

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

Receives the locations in the target's memory that correspond to the source lines queried for.  Each entry in this array is of type <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> and contains the source line number along with a location in the target's memory.


### -param EntriesCount [in]

Specifies the number of entries in the <i>Entries</i> array.


### -param EntriesAvail






#### - EntriesAvailable [out, optional]

Receives the number of locations that match the query found in the target's memory.


## -returns



These methods can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

For more information about source files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548339">GetSourceFileLineOffsets</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourceEntriesByLineWide method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

