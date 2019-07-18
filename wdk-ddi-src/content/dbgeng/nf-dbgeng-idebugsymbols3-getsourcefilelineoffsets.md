---
UID: NF:dbgeng.IDebugSymbols3.GetSourceFileLineOffsets
title: IDebugSymbols3::GetSourceFileLineOffsets (dbgeng.h)
description: The GetSourceFileLineOffsets method maps each line in a source file to a location in the target's memory.
old-location: debugger\getsourcefilelineoffsets.htm
tech.root: debugger
ms.assetid: ace9e23a-d7ea-480a-8001-f25310adee22
ms.date: 05/03/2018
ms.keywords: GetSourceFileLineOffsets, GetSourceFileLineOffsets method [Windows Debugging], GetSourceFileLineOffsets method [Windows Debugging],IDebugSymbols interface, GetSourceFileLineOffsets method [Windows Debugging],IDebugSymbols2 interface, GetSourceFileLineOffsets method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSourceFileLineOffsets method, IDebugSymbols2 interface [Windows Debugging],GetSourceFileLineOffsets method, IDebugSymbols2::GetSourceFileLineOffsets, IDebugSymbols3 interface [Windows Debugging],GetSourceFileLineOffsets method, IDebugSymbols3.GetSourceFileLineOffsets, IDebugSymbols3::GetSourceFileLineOffsets, IDebugSymbols::GetSourceFileLineOffsets, IDebugSymbols_18a64f21-a082-4953-8d69-2b3f7d805c60.xml, dbgeng/IDebugSymbols2::GetSourceFileLineOffsets, dbgeng/IDebugSymbols3::GetSourceFileLineOffsets, dbgeng/IDebugSymbols::GetSourceFileLineOffsets, debugger.getsourcefilelineoffsets
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols.GetSourceFileLineOffsets"
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
- IDebugSymbols.GetSourceFileLineOffsets
- IDebugSymbols2.GetSourceFileLineOffsets
- IDebugSymbols3.GetSourceFileLineOffsets
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSourceFileLineOffsets


## -description


The <b>GetSourceFileLineOffsets</b>  method maps each line in a source file to a location in the target's memory.


## -parameters




### -param File [in]

Specifies the name of the file whose lines will be turned into locations in the target's memory.  The symbols for each module in the target are queried for this file.  If the file is not located, the path is dropped and the symbols are queried again.


### -param Buffer [out, optional]

Receives the locations in the target's memory that correspond to the lines of the source code.  The first entry returned to this array corresponds to the first line of the file, so that <code>Buffer[i]</code> contains the location for line <code>i+1</code>.  If no symbol information is available for a line, the corresponding entry in <i>Buffer</i> is set to DEBUG_INVALID_OFFSET.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferLines [in]

Specifies the number of PULONG64 objects that the <i>Buffer</i> array can hold.


### -param FileLines [out, optional]

Receives the number of lines in the source file specified by <i>File</i>.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful.  However, the number of lines in the source file exceeded the number of entries in the <i>Buffer</i> array and some of the results were discarded.

</td>
</tr>
</table>
 




## -remarks



For more information about using the source path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-findsourcefile">FindSourceFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getsourceentriesbyline">GetSourceEntriesByLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

