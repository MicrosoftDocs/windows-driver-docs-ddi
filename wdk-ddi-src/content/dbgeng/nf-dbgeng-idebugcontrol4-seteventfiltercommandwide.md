---
UID: NF:dbgeng.IDebugControl4.SetEventFilterCommandWide
title: IDebugControl4::SetEventFilterCommandWide method
author: windows-driver-content
description: The SetEventFilterCommandWide method sets a debugger command for the engine to execute when a specified event occurs.
old-location: debugger\seteventfiltercommandwide.htm
old-project: debugger
ms.assetid: e0e14c8b-0b11-482f-93e2-31c522235110
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl4, IDebugControl4 interface [Windows Debugging], SetEventFilterCommandWide method, IDebugControl4::SetEventFilterCommandWide, SetEventFilterCommandWide method [Windows Debugging], SetEventFilterCommandWide method [Windows Debugging], IDebugControl4 interface, SetEventFilterCommandWide,IDebugControl4.SetEventFilterCommandWide, dbgeng/IDebugControl4::SetEventFilterCommandWide, debugger.seteventfiltercommandwide
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.SetEventFilterCommandWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::SetEventFilterCommandWide method


## -description


The <b>SetEventFilterCommandWide</b>  method sets a debugger command for the engine to execute when a specified event occurs.


## -syntax


````
HRESULT SetEventFilterCommandWide(
  [in] ULONG  Index,
  [in] PCWSTR Command
);
````


## -parameters




### -param Index [in]

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <b>GetNumberEventFilters</b> (inclusive).  For more information about the index of the filters, see Index and Exception Code.


### -param Command [in]

Specifies the debugger command for the engine to execute when the event occurs.


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




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556687">SetExceptionFilterSecondCommand</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546611">GetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



 

 


