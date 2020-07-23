---
UID: NF:dbgeng.IDebugControl3.GetNumberEventFilters
title: IDebugControl3::GetNumberEventFilters (dbgeng.h)
description: The GetNumberEventFilters method returns the number of event filters currently used by the engine.
old-location: debugger\getnumbereventfilters.htm
tech.root: debugger
ms.assetid: 6bb80c64-bb2e-4388-b1a8-479bdaa8b635
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetNumberEventFilters"]
ms.keywords: GetNumberEventFilters, GetNumberEventFilters method [Windows Debugging], GetNumberEventFilters method [Windows Debugging],IDebugControl interface, GetNumberEventFilters method [Windows Debugging],IDebugControl2 interface, GetNumberEventFilters method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNumberEventFilters method, IDebugControl2 interface [Windows Debugging],GetNumberEventFilters method, IDebugControl2::GetNumberEventFilters, IDebugControl3 interface [Windows Debugging],GetNumberEventFilters method, IDebugControl3.GetNumberEventFilters, IDebugControl3::GetNumberEventFilters, IDebugControl::GetNumberEventFilters, IDebugControl_de1a980a-b0cb-486b-a292-1a9463a231c6.xml, dbgeng/IDebugControl2::GetNumberEventFilters, dbgeng/IDebugControl3::GetNumberEventFilters, dbgeng/IDebugControl::GetNumberEventFilters, debugger.getnumbereventfilters
f1_keywords:
 - "dbgeng/IDebugControl.GetNumberEventFilters"
 - "IDebugControl.GetNumberEventFilters"
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
- IDebugControl.GetNumberEventFilters
- IDebugControl2.GetNumberEventFilters
- IDebugControl3.GetNumberEventFilters
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetNumberEventFilters


## -description


The <b>GetNumberEventFilters</b> method returns the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">event filters</a> currently used by the engine.


## -parameters




### -param SpecificEvents [out]

Receives the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/events">events</a> that can be controlled using the specific event filters.  These events are enumerated using some of the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">DEBUG_FILTER_XXX</a> constants.


### -param SpecificExceptions [out]

Receives the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/">exceptions</a> that can be controlled using the specific exception filters.  The first specific exception filter is the default exception filter.  The exceptions controlled by the other specific exception filters will always have their own filter and will not inherit their behavior from the default specific exception filter.  These exception filters are identified by their exception code.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/specific-exceptions">Specific Exceptions</a> for a list of the specific exception filters.


### -param ArbitraryExceptions [out]

Receives the number of arbitrary exception filters currently used by the engine.  These exception filters are identified by their exception code.


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



For more information about event filters, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.



