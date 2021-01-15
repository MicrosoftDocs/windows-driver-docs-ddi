---
UID: NF:dbgeng.IDebugClient5.GetDumpFileWide
title: IDebugClient5::GetDumpFileWide (dbgeng.h)
description: The GetDumpFileWide method describes the files containing supporting information that were used when opening the current dump target.
old-location: debugger\getdumpfilewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetDumpFileWide"]
ms.keywords: GetDumpFileWide, GetDumpFileWide method [Windows Debugging], GetDumpFileWide method [Windows Debugging],IDebugClient4 interface, GetDumpFileWide method [Windows Debugging],IDebugClient5 interface, IDebugClient4 interface [Windows Debugging],GetDumpFileWide method, IDebugClient4::GetDumpFileWide, IDebugClient5 interface [Windows Debugging],GetDumpFileWide method, IDebugClient5.GetDumpFileWide, IDebugClient5::GetDumpFileWide, dbgeng/IDebugClient4::GetDumpFileWide, dbgeng/IDebugClient5::GetDumpFileWide, debugger.getdumpfilewide
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
 - IDebugClient5::GetDumpFileWide
 - dbgeng/IDebugClient5::GetDumpFileWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5::GetDumpFileWide
---

# IDebugClient5::GetDumpFileWide


## -description

The <b>GetDumpFileWide</b> method describes the files containing supporting information that were used when opening the current dump target.

## -parameters

### -param Index 

[in]
Specifies which file to describe.  <i>Index</i> can take values between zero and the number of files minus one; the number of files can be found by using <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumberdumpfiles">GetNumberDumpFiles</a>.

### -param Buffer 

[out, optional]
Receives the file name.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size in characters of the buffer <i>Buffer</i>.

### -param NameSize 

[out, optional]
Receives the size of the file name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

### -param Handle 

[out, optional]
Receives the file handle of the file.  If <i>Handle</i> is <b>NULL</b>, this information is not returned.

### -param Type 

[out]
Receives the type of the file.

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



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumberdumpfiles">GetNumberDumpFiles</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>

