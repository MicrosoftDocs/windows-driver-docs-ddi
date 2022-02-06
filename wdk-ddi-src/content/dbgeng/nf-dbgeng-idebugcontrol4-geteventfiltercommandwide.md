---
UID: NF:dbgeng.IDebugControl4.GetEventFilterCommandWide
title: IDebugControl4::GetEventFilterCommandWide (dbgeng.h)
description: The GetEventFilterCommandWide method returns the debugger command that the engine will execute when a specified event occurs.
old-location: debugger\geteventfiltercommandwide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugControl4::GetEventFilterCommandWide"]
ms.keywords: GetEventFilterCommandWide, GetEventFilterCommandWide method [Windows Debugging], GetEventFilterCommandWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetEventFilterCommandWide method, IDebugControl4.GetEventFilterCommandWide, IDebugControl4::GetEventFilterCommandWide, dbgeng/IDebugControl4::GetEventFilterCommandWide, debugger.geteventfiltercommandwide
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
 - IDebugControl4::GetEventFilterCommandWide
 - dbgeng/IDebugControl4::GetEventFilterCommandWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4::GetEventFilterCommandWide
---

# IDebugControl4::GetEventFilterCommandWide


## -description

The <b>GetEventFilterCommandWide</b>  method returns the debugger command that the engine will execute when a specified event occurs.

## -parameters

### -param Index [in]


Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumbereventfilters">GetNumberEventFilters</a> (inclusive).  For more information about the index of the filters, see Index and Exception Code.

### -param Buffer [out, optional]


Receives the debugger command that the engine will execute when the event occurs.

### -param BufferSize [in]


Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param CommandSize [out, optional]


Receives the size in characters of the command. This size includes the space for the '\0' terminating character. If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.

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

For more information about event filters, see <a href="/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfiltersecondcommand">GetExceptionFilterSecondCommand</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-seteventfiltercommand">SetEventFilterCommand</a>



<a href="/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

