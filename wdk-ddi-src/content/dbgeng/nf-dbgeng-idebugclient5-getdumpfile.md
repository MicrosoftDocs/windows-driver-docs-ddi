---
UID: NF:dbgeng.IDebugClient5.GetDumpFile
title: IDebugClient5::GetDumpFile (dbgeng.h)
description: The IDebugClient5::GetDumpFile method describes the files containing supporting information that were used when opening the current dump target.
old-location: debugger\getdumpfile.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugClient5::GetDumpFile"]
ms.keywords: GetDumpFile, GetDumpFile method [Windows Debugging], GetDumpFile method [Windows Debugging],IDebugClient4 interface, GetDumpFile method [Windows Debugging],IDebugClient5 interface, IDebugClient4 interface [Windows Debugging],GetDumpFile method, IDebugClient4::GetDumpFile, IDebugClient5 interface [Windows Debugging],GetDumpFile method, IDebugClient5.GetDumpFile, IDebugClient5::GetDumpFile, IDebugClient_f4f1540c-116c-4e74-ad19-10beb0ac2739.xml, dbgeng/IDebugClient4::GetDumpFile, dbgeng/IDebugClient5::GetDumpFile, debugger.getdumpfile
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
 - IDebugClient5::GetDumpFile
 - dbgeng/IDebugClient5::GetDumpFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5::GetDumpFile
---

# IDebugClient5::GetDumpFile


## -description

The <b>GetDumpFile</b>  method describes the files containing supporting information that were used when opening the current dump target.

## -parameters

### -param Index [in]


Specifies which file to describe.  <i>Index</i> can take values between zero and the number of files minus one; the number of files can be found by using <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumberdumpfiles">GetNumberDumpFiles</a>.

### -param Buffer [out, optional]


Receives the file name.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize [in]


Specifies the size in characters of the buffer <i>Buffer</i>. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


Receives the size of the file name. This size includes the space for the '\0' terminating character. If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

### -param Handle [out, optional]


Receives the file handle of the file.  If <i>Handle</i> is <b>NULL</b>, this information is not returned.

### -param Type [out]


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

