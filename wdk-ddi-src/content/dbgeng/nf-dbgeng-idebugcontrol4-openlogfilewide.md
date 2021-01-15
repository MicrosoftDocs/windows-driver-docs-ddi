---
UID: NF:dbgeng.IDebugControl4.OpenLogFileWide
title: IDebugControl4::OpenLogFileWide (dbgeng.h)
description: The OpenLogFileWide method opens a log file that will receive output from the client objects.
old-location: debugger\openlogfilewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl4::OpenLogFileWide"]
ms.keywords: IDebugControl4 interface [Windows Debugging],OpenLogFileWide method, IDebugControl4.OpenLogFileWide, IDebugControl4::OpenLogFileWide, OpenLogFileWide, OpenLogFileWide method [Windows Debugging], OpenLogFileWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::OpenLogFileWide, debugger.openlogfilewide
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
 - IDebugControl4::OpenLogFileWide
 - dbgeng/IDebugControl4::OpenLogFileWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4::OpenLogFileWide
---

# IDebugControl4::OpenLogFileWide


## -description

The <b>OpenLogFileWide</b>  method opens a log file that will receive output from the <a href="/windows-hardware/drivers/debugger/client-objects">client objects</a>.

## -parameters

### -param File 

[in]
Specifies the name of the log file.  <i>File</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger  was started.  If the file does not exist, it will be created.

### -param Append 

[in]
Specifies whether or not to append log messages to an existing log file.  If <b>TRUE</b>, log messages will be appended to the file; if <b>FALSE</b>, the contents of any existing file matching <i>File</i> are discarded.

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

<b>OpenLogFile</b> and <b>OpenLogFileWide</b> behave the same way as <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a> and <b>OpenLogFile2Wide</b> with <i>Flags</i> set to DEBUG_LOG_APPEND if <i>Append</i> is <b>TRUE</b> and DEBUG_LOG_DEFAULT otherwise.

Only one log file can be open at a time.  If there is already a log file open, it will be closed.

For more information about log files, see <a href="/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/debugger/-logappend--append-log-file-">.logappend (Append Log File)</a>



<a href="/windows-hardware/drivers/debugger/-logopen--open-log-file-">.logopen (Open Log File)</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-closelogfile">CloseLogFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogfile">GetLogFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setlogmask">SetLogMask</a>

