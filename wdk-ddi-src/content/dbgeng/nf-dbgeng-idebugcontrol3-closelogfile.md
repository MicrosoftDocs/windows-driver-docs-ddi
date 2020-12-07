---
UID: NF:dbgeng.IDebugControl3.CloseLogFile
title: IDebugControl3::CloseLogFile (dbgeng.h)
description: The CloseLogFile method closes the currently-open log file.
old-location: debugger\closelogfile.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::CloseLogFile"]
ms.keywords: CloseLogFile, CloseLogFile method [Windows Debugging], CloseLogFile method [Windows Debugging],IDebugControl interface, CloseLogFile method [Windows Debugging],IDebugControl2 interface, CloseLogFile method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],CloseLogFile method, IDebugControl2 interface [Windows Debugging],CloseLogFile method, IDebugControl2::CloseLogFile, IDebugControl3 interface [Windows Debugging],CloseLogFile method, IDebugControl3.CloseLogFile, IDebugControl3::CloseLogFile, IDebugControl::CloseLogFile, IDebugControl_988fe3ac-a51d-4757-995d-40fe9d66aa02.xml, dbgeng/IDebugControl2::CloseLogFile, dbgeng/IDebugControl3::CloseLogFile, dbgeng/IDebugControl::CloseLogFile, debugger.closelogfile
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
 - IDebugControl3::CloseLogFile
 - dbgeng/IDebugControl3::CloseLogFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl.CloseLogFile
 - IDebugControl2.CloseLogFile
 - IDebugControl3.CloseLogFile
---

# IDebugControl3::CloseLogFile


## -description

The <b>CloseLogFile</b> method closes the currently-open log file.

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
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

If no log file is open, this method has no effect.

For more about log files, see <a href="/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/debugger/-logclose--close-log-file-">.logclose</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogfile">GetLogFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getlogfile2">GetLogFile2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-openlogfile">OpenLogFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>
