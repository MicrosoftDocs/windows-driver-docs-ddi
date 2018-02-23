---
UID: NF:dbgeng.IDebugControl2.GetNumberEventFilters
title: IDebugControl2::GetNumberEventFilters method
author: windows-driver-content
description: The GetNumberEventFilters method returns the number of event filters currently used by the engine.
old-location: debugger\getnumbereventfilters.htm
old-project: debugger
ms.assetid: 6bb80c64-bb2e-4388-b1a8-479bdaa8b635
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDebugControl2::GetNumberEventFilters, IDebugControl_de1a980a-b0cb-486b-a292-1a9463a231c6.xml, IDebugControl3::GetNumberEventFilters, IDebugControl::GetNumberEventFilters, GetNumberEventFilters method [Windows Debugging], IDebugControl2 interface, GetNumberEventFilters, GetNumberEventFilters method [Windows Debugging], IDebugControl interface, debugger.getnumbereventfilters, IDebugControl2 interface [Windows Debugging], GetNumberEventFilters method, GetNumberEventFilters method [Windows Debugging], IDebugControl interface [Windows Debugging], GetNumberEventFilters method, dbgeng/IDebugControl2::GetNumberEventFilters, IDebugControl, GetNumberEventFilters method [Windows Debugging], IDebugControl3 interface, IDebugControl2, IDebugControl3 interface [Windows Debugging], GetNumberEventFilters method, dbgeng/IDebugControl::GetNumberEventFilters, dbgeng/IDebugControl3::GetNumberEventFilters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.GetNumberEventFilters
-	IDebugControl2.GetNumberEventFilters
-	IDebugControl3.GetNumberEventFilters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetNumberEventFilters method


## -description


The <b>GetNumberEventFilters</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a> currently used by the engine.


## -syntax


````
HRESULT GetNumberEventFilters(
  [out] PULONG SpecificEvents,
  [out] PULONG SpecificExceptions,
  [out] PULONG ArbitraryExceptions
);
````


## -parameters




### -param SpecificEvents [out]

Receives the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a> that can be controlled using the specific event filters.  These events are enumerated using some of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541490">DEBUG_FILTER_XXX</a> constants.


### -param SpecificExceptions [out]

Receives the number of <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exceptions</a> that can be controlled using the specific exception filters.  The first specific exception filter is the default exception filter.  The exceptions controlled by the other specific exception filters will always have their own filter and will not inherit their behavior from the default specific exception filter.  These exception filters are identified by their exception code.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff558784">Specific Exceptions</a> for a list of the specific exception filters.


### -param ArbitraryExceptions [out]

Receives the number of arbitrary exception filters currently used by the engine.  These exception filters are identified by their exception code.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For more information about event filters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.



