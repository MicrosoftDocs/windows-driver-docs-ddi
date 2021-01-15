---
UID: NF:dbgeng.IDebugControl.SetLogMask
title: IDebugControl::SetLogMask (dbgeng.h)
description: The SetLogMask method sets the output mask for the currently open log file.
old-location: debugger\setlogmask.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl::SetLogMask"]
ms.keywords: IDebugControl interface [Windows Debugging],SetLogMask method, IDebugControl.SetLogMask, IDebugControl2 interface [Windows Debugging],SetLogMask method, IDebugControl2::SetLogMask, IDebugControl3 interface [Windows Debugging],SetLogMask method, IDebugControl3::SetLogMask, IDebugControl::SetLogMask, IDebugControl_b1c44a2b-d2fd-407b-8994-00f5e53af10d.xml, SetLogMask, SetLogMask method [Windows Debugging], SetLogMask method [Windows Debugging],IDebugControl interface, SetLogMask method [Windows Debugging],IDebugControl2 interface, SetLogMask method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetLogMask, dbgeng/IDebugControl3::SetLogMask, dbgeng/IDebugControl::SetLogMask, debugger.setlogmask
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
 - IDebugControl::SetLogMask
 - dbgeng/IDebugControl::SetLogMask
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl::SetLogMask
---

# IDebugControl::SetLogMask


## -description

The <b>SetLogMask</b> method sets the output mask for the currently open log file.

## -parameters

### -param Mask 

[in]
Specifies the new output mask for the log file.  See <a href="/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a> for details about this value.

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

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>

