---
UID: NF:dbgeng.IDebugControl3.GetLogMask
title: IDebugControl3::GetLogMask (dbgeng.h)
description: The GetLogMask method returns the output mask for the currently open log file.
old-location: debugger\getlogmask.htm
tech.root: debugger
ms.assetid: 32d36b6d-9887-43ac-9314-fc682705131e
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetLogMask"]
ms.keywords: GetLogMask, GetLogMask method [Windows Debugging], GetLogMask method [Windows Debugging],IDebugControl interface, GetLogMask method [Windows Debugging],IDebugControl2 interface, GetLogMask method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetLogMask method, IDebugControl2 interface [Windows Debugging],GetLogMask method, IDebugControl2::GetLogMask, IDebugControl3 interface [Windows Debugging],GetLogMask method, IDebugControl3.GetLogMask, IDebugControl3::GetLogMask, IDebugControl::GetLogMask, IDebugControl_a3ef306a-5134-49c7-b589-65a4afaa90ac.xml, dbgeng/IDebugControl2::GetLogMask, dbgeng/IDebugControl3::GetLogMask, dbgeng/IDebugControl::GetLogMask, debugger.getlogmask
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
 - IDebugControl3::GetLogMask
 - dbgeng/IDebugControl3::GetLogMask
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetLogMask
 - IDebugControl2.GetLogMask
 - IDebugControl3.GetLogMask
---

# IDebugControl3::GetLogMask


## -description

The <b>GetLogMask</b> method returns the output mask for the currently open log file.

## -parameters

### -param Mask 

[out]
Receives the output mask for the log file.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a> for details about how to interpret this value.

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

For more information about log files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setlogmask">SetLogMask</a>

