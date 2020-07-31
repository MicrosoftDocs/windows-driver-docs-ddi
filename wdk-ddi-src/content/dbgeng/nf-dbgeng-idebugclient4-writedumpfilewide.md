---
UID: NF:dbgeng.IDebugClient4.WriteDumpFileWide
title: IDebugClient4::WriteDumpFileWide (dbgeng.h)
description: The WriteDumpFileWide method creates a user-mode or kernel-modecrash dump file.
old-location: debugger\writedumpfilewide.htm
tech.root: debugger
ms.assetid: b089499f-4f15-400e-bf88-53d0507200b9
ms.date: 05/03/2018
keywords: ["IDebugClient4::WriteDumpFileWide"]
ms.keywords: IDebugClient4 interface [Windows Debugging],WriteDumpFileWide method, IDebugClient4.WriteDumpFileWide, IDebugClient4::WriteDumpFileWide, IDebugClient5 interface [Windows Debugging],WriteDumpFileWide method, IDebugClient5::WriteDumpFileWide, IDebugClient_cbae8215-df5f-484c-9b0a-8a5dc1564a00.xml, WriteDumpFileWide, WriteDumpFileWide method [Windows Debugging], WriteDumpFileWide method [Windows Debugging],IDebugClient4 interface, WriteDumpFileWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient4::WriteDumpFileWide, dbgeng/IDebugClient5::WriteDumpFileWide, debugger.writedumpfilewide
f1_keywords:
 - "dbgeng/IDebugClient4.WriteDumpFileWide"
 - "IDebugClient4.WriteDumpFileWide"
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
- IDebugClient4.WriteDumpFileWide
- IDebugClient5.WriteDumpFileWide
targetos: Windows
req.typenames: 
---

# IDebugClient4::WriteDumpFileWide


## -description


The <b>WriteDumpFileWide</b> method creates a user-mode or kernel-modecrash dump file.


## -parameters




### -param FileName [in, optional]

Specifies the name of the dump file to create.  <i>FileName</i> must include the file name extension. <i>FileName</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  If <i>FileHandle</i> is not <b>NULL</b>, <i>FileName</i> is ignored (except when writing status messages to the debugger console).


### -param FileHandle [in]

Specifies the file handle of the file to write the crash dump to.  If <i>FileHandle</i> is <b>NULL</b>, the file specified in <i>FileName</i> is used instead.


### -param Qualifier [in]

Specifies the type of dump to create.  For possible values, see <a href="https://docs.microsoft.com/previous-versions/ff541472(v=vs.85)">DEBUG_DUMP_XXX</a>.


### -param FormatFlags [in]

Specifies flags that determine the format of the dump file and--for user-mode minidumps--what information to include in the file.  For details, see <a href="https://docs.microsoft.com/previous-versions/ff541497(v=vs.85)">DEBUG_FORMAT_XXX</a>.


### -param Comment [in, optional]

Specifies a comment string to be included in the crash dump file.  This string is displayed in the debugger console when the dump file is loaded.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



For more information about crash dump files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/dump-file-targets">Dump-File Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-dump--create-dump-file-">.dump (Create Dump File)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfile2">WriteDumpFile2</a>
 

 

