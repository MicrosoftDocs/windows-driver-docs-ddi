---
UID: NF:dbgeng.IDebugControl4.GetExceptionFilterSecondCommand
title: IDebugControl4::GetExceptionFilterSecondCommand method (dbgeng.h)
description: The IDebugControl4::GetExceptionFilterSecondCommandWide method returns the command that will be executed upon the second chance of an exception.
old-location: debugger\getexceptionfiltersecondcommandwide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugControl4::GetExceptionFilterSecondCommand method"]
ms.keywords: GetExceptionFilterSecondCommand,IDebugControl4.GetExceptionFilterSecondCommand, GetExceptionFilterSecondCommandWide method [Windows Debugging], GetExceptionFilterSecondCommandWide method [Windows Debugging], IDebugControl4 interface, IDebugControl4, IDebugControl4 interface [Windows Debugging], GetExceptionFilterSecondCommandWide method, IDebugControl4::GetExceptionFilterSecondCommand, IDebugControl4::GetExceptionFilterSecondCommandWide, dbgeng/IDebugControl4::GetExceptionFilterSecondCommandWide, debugger.getexceptionfiltersecondcommandwide
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
f1_keywords:
 - IDebugControl4::GetExceptionFilterSecondCommand
 - dbgeng/IDebugControl4::GetExceptionFilterSecondCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4::GetExceptionFilterSecondCommand
---

# IDebugControl4::GetExceptionFilterSecondCommand method


## -description

The <b>GetExceptionFilterSecondCommandWide</b>  method returns the command that will be executed by the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> upon the second chance of a specified <a href="/windows-hardware/drivers/">exception</a>.

## -parameters

### -param Index [in]


Specifies the index of the exception filter whose second-chance command will be returned.  <i>Index</i> can also refer to the default exception filter to return the second-chance command for those exceptions that do not have a specific or arbitrary exception filter.

### -param Buffer [out, optional]


Receives the second-chance command for the exception filter.

### -param BufferSize [in]


Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param CommandSize [out, optional]


Receives the size, in characters, of the second-chance command for the exception filter. This size includes the space for the '\0' terminating character. If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.

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



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfiltersecondcommand">SetExceptionFilterSecondCommand</a>



<a href="/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

