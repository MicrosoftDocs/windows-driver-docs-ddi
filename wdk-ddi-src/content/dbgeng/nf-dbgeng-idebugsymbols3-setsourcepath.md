---
UID: NF:dbgeng.IDebugSymbols3.SetSourcePath
title: IDebugSymbols3::SetSourcePath (dbgeng.h)
description: The SetSourcePath method sets the source path.
old-location: debugger\setsourcepath.htm
tech.root: debugger
ms.assetid: 00b5927e-4b95-4528-bc09-da90db8a7716
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::SetSourcePath"]
ms.keywords: IDebugSymbols interface [Windows Debugging],SetSourcePath method, IDebugSymbols2 interface [Windows Debugging],SetSourcePath method, IDebugSymbols2::SetSourcePath, IDebugSymbols3 interface [Windows Debugging],SetSourcePath method, IDebugSymbols3.SetSourcePath, IDebugSymbols3::SetSourcePath, IDebugSymbols::SetSourcePath, IDebugSymbols_d592ec7c-56f9-46b2-9627-d79e8fdba5c4.xml, SetSourcePath, SetSourcePath method [Windows Debugging], SetSourcePath method [Windows Debugging],IDebugSymbols interface, SetSourcePath method [Windows Debugging],IDebugSymbols2 interface, SetSourcePath method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::SetSourcePath, dbgeng/IDebugSymbols3::SetSourcePath, dbgeng/IDebugSymbols::SetSourcePath, debugger.setsourcepath
f1_keywords:
 - "dbgeng/IDebugSymbols.SetSourcePath"
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
- IDebugSymbols.SetSourcePath
- IDebugSymbols2.SetSourcePath
- IDebugSymbols3.SetSourcePath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::SetSourcePath


## -description


The <b>SetSourcePath</b>  method sets the source path.


## -parameters




### -param Path [in]

Specifies the new source path.  This is a string that contains source path elements separated by semicolons (<b>;</b>).  Each source path element can specify either a directory or a source server.


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
</table>
 




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/source-path">Source Path</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendsourcepath">AppendSourcePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepath">GetSourcePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

