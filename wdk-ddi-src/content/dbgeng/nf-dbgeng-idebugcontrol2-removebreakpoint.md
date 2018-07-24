---
UID: NF:dbgeng.IDebugControl2.RemoveBreakpoint
title: IDebugControl2::RemoveBreakpoint
author: windows-driver-content
description: The RemoveBreakpoint method removes a breakpoint.
old-location: debugger\removebreakpoint.htm
tech.root: debugger
ms.assetid: ce0f5e42-3f4e-48e1-9e73-96bca96e8e23
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugControl interface [Windows Debugging],RemoveBreakpoint method, IDebugControl2 interface [Windows Debugging],RemoveBreakpoint method, IDebugControl2.RemoveBreakpoint, IDebugControl2::RemoveBreakpoint, IDebugControl3 interface [Windows Debugging],RemoveBreakpoint method, IDebugControl3::RemoveBreakpoint, IDebugControl::RemoveBreakpoint, IDebugControl_431f31ce-38fb-4350-851b-49b103047943.xml, RemoveBreakpoint, RemoveBreakpoint method [Windows Debugging], RemoveBreakpoint method [Windows Debugging],IDebugControl interface, RemoveBreakpoint method [Windows Debugging],IDebugControl2 interface, RemoveBreakpoint method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::RemoveBreakpoint, dbgeng/IDebugControl3::RemoveBreakpoint, dbgeng/IDebugControl::RemoveBreakpoint, debugger.removebreakpoint
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
-	IDebugControl.RemoveBreakpoint
-	IDebugControl2.RemoveBreakpoint
-	IDebugControl3.RemoveBreakpoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::RemoveBreakpoint


## -description


The <b>RemoveBreakpoint</b>  method removes a breakpoint.


## -parameters




### -param Bp [in]

Specifies an interface pointer to breakpoint to remove.


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
</table>
 

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



After <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called, the breakpoint object specified in the <i>Bp</i> parameter must not be used again.

<div class="alert"><b>Note</b>    Even though <a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called.</div>
<div> </div>
For more details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537856">AddBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

