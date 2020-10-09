---
UID: NF:dbgeng.IDebugSymbols3.GetSourcePath
title: IDebugSymbols3::GetSourcePath (dbgeng.h)
description: The GetSourcePath method returns the source path.
old-location: debugger\getsourcepath.htm
tech.root: debugger
ms.assetid: 93a1efce-5f93-4a09-aa61-ffbd3d619176
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSourcePath"]
ms.keywords: GetSourcePath, GetSourcePath method [Windows Debugging], GetSourcePath method [Windows Debugging],IDebugSymbols interface, GetSourcePath method [Windows Debugging],IDebugSymbols2 interface, GetSourcePath method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSourcePath method, IDebugSymbols2 interface [Windows Debugging],GetSourcePath method, IDebugSymbols2::GetSourcePath, IDebugSymbols3 interface [Windows Debugging],GetSourcePath method, IDebugSymbols3.GetSourcePath, IDebugSymbols3::GetSourcePath, IDebugSymbols::GetSourcePath, IDebugSymbols_cbdf5e16-41ba-4134-b41b-81164dfc07a0.xml, dbgeng/IDebugSymbols2::GetSourcePath, dbgeng/IDebugSymbols3::GetSourcePath, dbgeng/IDebugSymbols::GetSourcePath, debugger.getsourcepath
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
 - IDebugSymbols3::GetSourcePath
 - dbgeng/IDebugSymbols3::GetSourcePath
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.GetSourcePath
 - IDebugSymbols2.GetSourcePath
 - IDebugSymbols3.GetSourcePath
---

# IDebugSymbols3::GetSourcePath


## -description

The <b>GetSourcePath</b>  method returns the source path.

## -parameters

### -param Buffer 

[out, optional]
Receives the source path.  This is a string that contains source path elements separated by semicolons (<b>;</b>).  Each source path element can specify either a directory or a source server.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size, in characters, of the <i>Buffer</i> buffer.

### -param PathSize 

[out, optional]
Receives the size, in characters, of the source path.

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

For more information about manipulating the source path, see <a href="/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="/windows-hardware/drivers/debugger/source-path">Source Path</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepath">AppendSourcePath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepathelement">GetSourcePathElement</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setsourcepath">SetSourcePath</a>