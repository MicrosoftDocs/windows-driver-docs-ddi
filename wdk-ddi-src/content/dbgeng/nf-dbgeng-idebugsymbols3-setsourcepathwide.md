---
UID: NF:dbgeng.IDebugSymbols3.SetSourcePathWide
title: IDebugSymbols3::SetSourcePathWide (dbgeng.h)
description: The SetSourcePathWide method sets the source path.
old-location: debugger\setsourcepathwide.htm
tech.root: debugger
ms.assetid: 1fdb4e2c-ece7-407e-840c-fbd6dfe46d78
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::SetSourcePathWide"]
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetSourcePathWide method, IDebugSymbols3.SetSourcePathWide, IDebugSymbols3::SetSourcePathWide, SetSourcePathWide, SetSourcePathWide method [Windows Debugging], SetSourcePathWide method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetSourcePathWide, debugger.setsourcepathwide
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
 - IDebugSymbols3::SetSourcePathWide
 - dbgeng/IDebugSymbols3::SetSourcePathWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.SetSourcePathWide
---

# IDebugSymbols3::SetSourcePathWide


## -description

The <b>SetSourcePathWide</b>  method sets the source path.

## -parameters

### -param Path 

[in]
Specifies the new source path.  This is a string that contains source path elements separated by semicolons (<b>;</b>).  Each source path element can specify either a directory or a source server.

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

The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="/windows-hardware/drivers/debugger/source-path">Source Path</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepath">AppendSourcePath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepath">GetSourcePath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>