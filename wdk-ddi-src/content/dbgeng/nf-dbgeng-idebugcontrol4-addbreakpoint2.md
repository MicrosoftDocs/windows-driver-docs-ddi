---
UID: NF:dbgeng.IDebugControl4.AddBreakpoint2
title: IDebugControl4::AddBreakpoint2
author: windows-driver-content
description: The AddBreakpoint2 method creates a new breakpoint for the current target.
old-location: debugger\addbreakpoint2.htm
tech.root: debugger
ms.assetid: 001a64dd-1470-42e0-98ba-22ba33f3fa69
ms.date: 05/03/2018
ms.keywords: AddBreakpoint2, AddBreakpoint2 method [Windows Debugging], AddBreakpoint2 method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],AddBreakpoint2 method, IDebugControl4.AddBreakpoint2, IDebugControl4::AddBreakpoint2, dbgeng/IDebugControl4::AddBreakpoint2, debugger.addbreakpoint2
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
-	Dbgeng.h
api_name:
-	IDebugControl4.AddBreakpoint2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::AddBreakpoint2


## -description


The <b>AddBreakpoint2</b>  method creates a new breakpoint for the current target.


## -parameters




### -param Type [in]

Specifies the breakpoint type of the new breakpoint.  This can be either of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_CODE

</td>
<td>
<a href="https://msdn.microsoft.com/94cbf33b-e975-49eb-a266-774798955a48">software breakpoint</a>

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
<a href="https://msdn.microsoft.com/4cfad26c-d8c0-4f80-aa54-b9cadbc84df3">processor breakpoint</a>

</td>
</tr>
</table>
 


### -param DesiredId [in]

Specifies the desired ID of the new breakpoint.  If it is DEBUG_ANY_ID, the engine will pick an unused ID.


### -param Bp [out]

Receives an interface pointer to the new breakpoint.


## -returns



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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint couldn't be created with the desired ID or the value of <i>Type</i> was not recognized.

</td>
</tr>
</table>
 

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If <i>DesiredId</i> is not DEBUG_ANY_ID and another breakpoint already uses the ID <i>DesiredId</i>, these methods will fail.

Breakpoints are created empty and disabled.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a> for details on configuring and enabling the breakpoint.

The client is saved as the adder of the new breakpoint. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545576">GetAdder</a>. 

<div class="alert"><b>Note</b>    Even though <a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a> is called.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>
 

 

