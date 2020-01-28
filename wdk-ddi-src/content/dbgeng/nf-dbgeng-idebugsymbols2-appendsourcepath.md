---
UID: NF:dbgeng.IDebugSymbols2.AppendSourcePath
title: IDebugSymbols2::AppendSourcePath (dbgeng.h)
description: The AppendSourcePath method appends directories to the source path.
old-location: debugger\appendsourcepath.htm
tech.root: debugger
ms.assetid: b82c2206-b81d-4ebf-a8fd-c08d7f57ffc9
ms.date: 05/03/2018
ms.keywords: AppendSourcePath, AppendSourcePath method [Windows Debugging], AppendSourcePath method [Windows Debugging],IDebugSymbols interface, AppendSourcePath method [Windows Debugging],IDebugSymbols2 interface, AppendSourcePath method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],AppendSourcePath method, IDebugSymbols2 interface [Windows Debugging],AppendSourcePath method, IDebugSymbols2.AppendSourcePath, IDebugSymbols2::AppendSourcePath, IDebugSymbols3 interface [Windows Debugging],AppendSourcePath method, IDebugSymbols3::AppendSourcePath, IDebugSymbols::AppendSourcePath, IDebugSymbols_8e47c1ea-e190-4f34-a952-1dcf4ef9e971.xml, dbgeng/IDebugSymbols2::AppendSourcePath, dbgeng/IDebugSymbols3::AppendSourcePath, dbgeng/IDebugSymbols::AppendSourcePath, debugger.appendsourcepath
f1_keywords:
 - "dbgeng/IDebugSymbols.AppendSourcePath"
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
- Dbgeng.h
api_name:
- IDebugSymbols.AppendSourcePath
- IDebugSymbols2.AppendSourcePath
- IDebugSymbols3.AppendSourcePath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::AppendSourcePath


## -description


The <b>AppendSourcePath</b>  method appends directories to the source path.


## -parameters




### -param Addition [in]

Specifies the directories to append to the source path.  This is a string that contains source path elements separated by semicolons (;).  Each source path element can specify either a directory or a source server.


## -returns



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
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/source-path">Source Path</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepath">GetSourcePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsourcepathelement">GetSourcePathElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setsourcepath">SetSourcePath</a>
 

 

