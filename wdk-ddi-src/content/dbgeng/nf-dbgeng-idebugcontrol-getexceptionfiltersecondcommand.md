---
UID: NF:dbgeng.IDebugControl.GetExceptionFilterSecondCommand
title: IDebugControl::GetExceptionFilterSecondCommand (dbgeng.h)
description: The GetExceptionFilterSecondCommand method returns the command that will be executed by the debugger engine upon the second chance of a specified exception.
old-location: debugger\getexceptionfiltersecondcommand.htm
tech.root: debugger
ms.assetid: 1ea607e2-76a2-4f78-87ca-bf3242f39433
ms.date: 05/03/2018
keywords: ["IDebugControl::GetExceptionFilterSecondCommand"]
ms.keywords: GetExceptionFilterSecondCommand, GetExceptionFilterSecondCommand method [Windows Debugging], GetExceptionFilterSecondCommand method [Windows Debugging],IDebugControl interface, GetExceptionFilterSecondCommand method [Windows Debugging],IDebugControl2 interface, GetExceptionFilterSecondCommand method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExceptionFilterSecondCommand method, IDebugControl.GetExceptionFilterSecondCommand, IDebugControl2 interface [Windows Debugging],GetExceptionFilterSecondCommand method, IDebugControl2::GetExceptionFilterSecondCommand, IDebugControl3 interface [Windows Debugging],GetExceptionFilterSecondCommand method, IDebugControl3::GetExceptionFilterSecondCommand, IDebugControl::GetExceptionFilterSecondCommand, IDebugControl_fba6b716-8dba-4581-87c3-b808d3ab40a1.xml, dbgeng/IDebugControl2::GetExceptionFilterSecondCommand, dbgeng/IDebugControl3::GetExceptionFilterSecondCommand, dbgeng/IDebugControl::GetExceptionFilterSecondCommand, debugger.getexceptionfiltersecondcommand
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
 - IDebugControl::GetExceptionFilterSecondCommand
 - dbgeng/IDebugControl::GetExceptionFilterSecondCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetExceptionFilterSecondCommand
 - IDebugControl2.GetExceptionFilterSecondCommand
 - IDebugControl3.GetExceptionFilterSecondCommand
---

# IDebugControl::GetExceptionFilterSecondCommand


## -description

The <b>GetExceptionFilterSecondCommand</b>  method returns the command that will be executed by the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> upon the second chance of a specified <a href="/windows-hardware/drivers/">exception</a>.

## -parameters

### -param Index 

[in]
Specifies the index of the exception filter whose second-chance command will be returned.  <i>Index</i> can also refer to the default exception filter to return the second-chance command for those exceptions that do not have a specific or arbitrary exception filter.

### -param Buffer 

[out, optional]
Receives the second-chance command for the exception filter.

### -param BufferSize 

[in]
Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.

### -param CommandSize 

[out, optional]
Receives the size, in characters, of the second-chance command for the exception filter.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.

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

Only exception filters support a second-chance command.  If <i>Index</i> refers to a <a href="/windows-hardware/drivers/debugger/debug-filter-xxx">specific event filter</a>, the command returned to <i>Buffer</i> will be empty.  The returned command will also be empty if no second-chance command has been set for the specified exception.

For more information about <a href="/windows-hardware/drivers/debugger/event-filters">event filters</a>, see <a href="/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-geteventfiltercommand">GetEventFilterCommand</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfiltersecondcommand">SetExceptionFilterSecondCommand</a>



<a href="/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>