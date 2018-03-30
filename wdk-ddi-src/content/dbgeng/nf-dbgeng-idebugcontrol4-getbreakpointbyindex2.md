---
UID: NF:dbgeng.IDebugControl4.GetBreakpointByIndex2
title: IDebugControl4::GetBreakpointByIndex2 method
author: windows-driver-content
description: The GetBreakpointByIndex2 method returns the breakpoint located at the specified index.
old-location: debugger\getbreakpointbyindex2.htm
old-project: debugger
ms.assetid: 3487addb-e196-4295-95fc-0590802e766a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetBreakpointByIndex2 method [Windows Debugging], GetBreakpointByIndex2 method [Windows Debugging], IDebugControl4 interface, GetBreakpointByIndex2,IDebugControl4.GetBreakpointByIndex2, IDebugControl4, IDebugControl4 interface [Windows Debugging], GetBreakpointByIndex2 method, IDebugControl4::GetBreakpointByIndex2, dbgeng/IDebugControl4::GetBreakpointByIndex2, debugger.getbreakpointbyindex2
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
-	IDebugControl4.GetBreakpointByIndex2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::GetBreakpointByIndex2 method


## -description


The <b>GetBreakpointByIndex2</b>  method returns the breakpoint located at the specified index.


## -parameters




### -param Index [in]

Specifies the zero-based index of the breakpoint to return.  This is specific to the current process.  The value of <i>Index</i> should be between zero and the total number of breakpoints minus one. The total number of breakpoints can be determined by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547880">GetNumberBreakpoints</a>.


### -param Bp [out]

Receives the returned breakpoint.


## -returns



This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No breakpoint was found with the given index, or the breakpoint with the given index is private.

</td>
</tr>
</table>
 




## -remarks



The index and returned breakpoint are specific to the current process.  The same index will return a different breakpoint if the current process is changed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547880">GetNumberBreakpoints</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

