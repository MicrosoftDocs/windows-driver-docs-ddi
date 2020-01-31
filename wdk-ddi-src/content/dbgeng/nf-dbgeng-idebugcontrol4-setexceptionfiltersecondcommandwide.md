---
UID: NF:dbgeng.IDebugControl4.SetExceptionFilterSecondCommandWide
title: IDebugControl4::SetExceptionFilterSecondCommandWide (dbgeng.h)
description: The SetExceptionFilterSecondCommandWide method sets the command that will be executed by the debugger engine on the second chance of a specified exception.
old-location: debugger\setexceptionfiltersecondcommandwide.htm
tech.root: debugger
ms.assetid: cbc0e98b-eac7-441d-b2b5-512725403210
ms.date: 05/03/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],SetExceptionFilterSecondCommandWide method, IDebugControl4.SetExceptionFilterSecondCommandWide, IDebugControl4::SetExceptionFilterSecondCommandWide, SetExceptionFilterSecondCommandWide, SetExceptionFilterSecondCommandWide method [Windows Debugging], SetExceptionFilterSecondCommandWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetExceptionFilterSecondCommandWide, debugger.setexceptionfiltersecondcommandwide
f1_keywords:
 - "dbgeng/IDebugControl4.SetExceptionFilterSecondCommandWide"
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
- IDebugControl4.SetExceptionFilterSecondCommandWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::SetExceptionFilterSecondCommandWide


## -description


The <b>SetExceptionFilterSecondCommandWide</b>  method sets the command that will be executed by the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> on the second chance of a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/">exception</a>.


## -parameters




### -param Index [in]

Specifies the index of the exception filter whose second-chance command will be set.  <i>Index</i> must not refer to the specific event filters as these are not exception filters and only exception events get a second chance.  If <i>Index</i> refers to the default exception filter, the second-chance command is set for all exceptions that do not have an exception filter.


### -param Command [in]

Receives the second-chance command for the exception filter.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



For more information about <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">event filters</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfiltersecondcommand">GetExceptionFilterSecondCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-seteventfiltercommand">SetEventFilterCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

