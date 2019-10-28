---
UID: NF:dbgeng.IDebugControl4.OpenLogFile2
title: IDebugControl4::OpenLogFile2 (dbgeng.h)
description: The OpenLogFile2 method opens a log file that will receive output from the client objects.
old-location: debugger\openlogfile2.htm
tech.root: debugger
ms.assetid: 58550baa-8d15-43c7-b75d-1370c36e833d
ms.date: 05/03/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],OpenLogFile2 method, IDebugControl4.OpenLogFile2, IDebugControl4::OpenLogFile2, IDebugControl_93e0a810-9b23-43c2-b714-99a39c398f1e.xml, OpenLogFile2, OpenLogFile2 method [Windows Debugging], OpenLogFile2 method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::OpenLogFile2, debugger.openlogfile2
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl4.OpenLogFile2"
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
- IDebugControl4.OpenLogFile2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::OpenLogFile2


## -description


The <b>OpenLogFile2</b>  method opens a log file that will receive output from the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">client objects</a>.


## -parameters




### -param File [in]

Specifies the name of the log file.  <i>File</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger  was started.  If the file does not exist, it will be created.


### -param Flags [in]

Specifies the bit-flags that control the nature of the log file.  <i>Flags</i> can contain flags from the following table.

<table>
<tr>
<th>Flag</th>
<th>Effect when set</th>
</tr>
<tr>
<td>
DEBUG_LOG_APPEND

</td>
<td>
Output will be appended to the log file instead of discarding the contents of the log file.

</td>
</tr>
<tr>
<td>
DEBUG_LOG_UNICODE

</td>
<td>
The format of the log file will be Unicode instead of ASCII.

</td>
</tr>
</table>
 

Alternatively, <i>Flags</i> can be set to DEBUG_LOG_DEFAULT for the default set of options that contains none of the flags.


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



Only one log file can be open at a time.  If there is already a log file open, it will be closed.

For more information about log files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-logappend--append-log-file-">.logappend (Append Log File)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-logopen--open-log-file-">.logopen (Open Log File)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-closelogfile">CloseLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getlogfile2">GetLogFile2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-openlogfile">OpenLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setlogmask">SetLogMask</a>
 

 

