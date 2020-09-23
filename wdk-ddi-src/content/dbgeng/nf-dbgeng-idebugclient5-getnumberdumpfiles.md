---
UID: NF:dbgeng.IDebugClient5.GetNumberDumpFiles
title: IDebugClient5::GetNumberDumpFiles (dbgeng.h)
description: The GetNumberDumpFiles method returns the number of files containing supporting information that were used when opening the current dump target.
old-location: debugger\getnumberdumpfiles.htm
tech.root: debugger
ms.assetid: d3fa4314-2f11-4ac4-86bd-3eb3f3ea9029
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetNumberDumpFiles"]
ms.keywords: GetNumberDumpFiles, GetNumberDumpFiles method [Windows Debugging], GetNumberDumpFiles method [Windows Debugging],IDebugClient4 interface, GetNumberDumpFiles method [Windows Debugging],IDebugClient5 interface, IDebugClient4 interface [Windows Debugging],GetNumberDumpFiles method, IDebugClient4::GetNumberDumpFiles, IDebugClient5 interface [Windows Debugging],GetNumberDumpFiles method, IDebugClient5.GetNumberDumpFiles, IDebugClient5::GetNumberDumpFiles, IDebugClient_db74cf2c-c7e7-46c2-be98-f4023b22c5c3.xml, dbgeng/IDebugClient4::GetNumberDumpFiles, dbgeng/IDebugClient5::GetNumberDumpFiles, debugger.getnumberdumpfiles
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
 - IDebugClient5::GetNumberDumpFiles
 - dbgeng/IDebugClient5::GetNumberDumpFiles
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient4.GetNumberDumpFiles
 - IDebugClient5.GetNumberDumpFiles
---

# IDebugClient5::GetNumberDumpFiles


## -description

The <b>GetNumberDumpFiles</b> method returns the number of files containing supporting information that were used when opening the current dump target.

## -parameters

### -param Number 

[out]
Receives the number of files.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about crash dump files, see <a href="/windows-hardware/drivers/debugger/dump-file-targets">Dump-File Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfile">AddDumpInformationFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfilewide">AddDumpInformationFileWide</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getdumpfile">GetDumpFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>