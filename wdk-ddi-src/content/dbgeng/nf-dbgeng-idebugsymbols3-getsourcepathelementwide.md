---
UID: NF:dbgeng.IDebugSymbols3.GetSourcePathElementWide
title: IDebugSymbols3::GetSourcePathElementWide (dbgeng.h)
description: The GetSourcePathElementWide method returns an element from the source path.
old-location: debugger\getsourcepathelementwide.htm
tech.root: debugger
ms.assetid: 724ee7a6-a0ef-440b-a0d4-5eecda77338a
ms.date: 05/03/2018
ms.keywords: GetSourcePathElementWide, GetSourcePathElementWide method [Windows Debugging], GetSourcePathElementWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourcePathElementWide method, IDebugSymbols3.GetSourcePathElementWide, IDebugSymbols3::GetSourcePathElementWide, dbgeng/IDebugSymbols3::GetSourcePathElementWide, debugger.getsourcepathelementwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetSourcePathElementWide"
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
- IDebugSymbols3.GetSourcePathElementWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSourcePathElementWide


## -description


The <b>GetSourcePathElementWide</b>  method returns an element from the source path.


## -parameters




### -param Index [in]

Specifies the index of the element in the source path that will be returned.  The source path is a string that contains elements separated by semicolons (;).  The index of the first element is zero.


### -param Buffer [out, optional]

Receives the source path element.  Each source path element can be a directory or a source server.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param ElementSize [out, optional]

Receives the size, in characters, of the source path element.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The source path contains fewer than <i>Index</i> elements.

</td>
</tr>
</table>
 




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/source-path">Source Path</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepath">AppendSourcePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepath">GetSourcePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

