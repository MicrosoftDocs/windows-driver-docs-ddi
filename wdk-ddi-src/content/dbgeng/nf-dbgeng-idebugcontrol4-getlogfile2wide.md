---
UID: NF:dbgeng.IDebugControl4.GetLogFile2Wide
title: IDebugControl4::GetLogFile2Wide (dbgeng.h)
description: The GetLogFile2Wide method returns the name of the currently open log file.
old-location: debugger\getlogfile2wide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetLogFile2Wide"]
ms.keywords: GetLogFile2Wide, GetLogFile2Wide method [Windows Debugging], GetLogFile2Wide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetLogFile2Wide method, IDebugControl4.GetLogFile2Wide, IDebugControl4::GetLogFile2Wide, dbgeng/IDebugControl4::GetLogFile2Wide, debugger.getlogfile2wide
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
 - IDebugControl4::GetLogFile2Wide
 - dbgeng/IDebugControl4::GetLogFile2Wide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.GetLogFile2Wide
---

# IDebugControl4::GetLogFile2Wide


## -description

The <b>GetLogFile2Wide</b>  method returns the name of the currently open log file.

## -parameters

### -param Buffer 

[out, optional]
Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size, in characters, of the <i>Buffer</i> buffer.

### -param FileSize 

[out, optional]
Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.

### -param Flags 

[out]
Receives the bit-flags that were used when opening the log file.  See the <i>Flags</i> parameter of <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a> for a description of these flags.

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
The method was successful.  However, the name of the log file was too long to fit in the <i>Buffer</i> buffer so the name was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
There is no currently open log file.

</td>
</tr>
</table>

## -remarks

For more information about log files, see <a href="/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-closelogfile">CloseLogFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogfile">GetLogFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>
