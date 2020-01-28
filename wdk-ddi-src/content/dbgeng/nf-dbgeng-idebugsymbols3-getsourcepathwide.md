---
UID: NF:dbgeng.IDebugSymbols3.GetSourcePathWide
title: IDebugSymbols3::GetSourcePathWide (dbgeng.h)
description: The GetSourcePathWide method returns the source path.
old-location: debugger\getsourcepathwide.htm
tech.root: debugger
ms.assetid: 6c9c8270-78c4-4bc2-a0e4-5c5e245326ad
ms.date: 05/03/2018
ms.keywords: GetSourcePathWide, GetSourcePathWide method [Windows Debugging], GetSourcePathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourcePathWide method, IDebugSymbols3.GetSourcePathWide, IDebugSymbols3::GetSourcePathWide, dbgeng/IDebugSymbols3::GetSourcePathWide, debugger.getsourcepathwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetSourcePathWide"
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
- IDebugSymbols3.GetSourcePathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSourcePathWide


## -description


The <b>GetSourcePathWide</b>  method returns the source path.


## -parameters




### -param Buffer [out, optional]

Receives the source path.  This is a string that contains source path elements separated by semicolons (<b>;</b>).  Each source path element can specify either a directory or a source server.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param PathSize [out, optional]

Receives the size, in characters, of the source path.


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
The method was successful. However, the buffer was not large enough to hold the source path and the path was truncated.

</td>
</tr>
</table>
 




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/source-path">Source Path</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepath">AppendSourcePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepathelement">GetSourcePathElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setsourcepath">SetSourcePath</a>
 

 

