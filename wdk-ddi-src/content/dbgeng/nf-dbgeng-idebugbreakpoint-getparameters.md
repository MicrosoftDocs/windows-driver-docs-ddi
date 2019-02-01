---
UID: NF:dbgeng.IDebugBreakpoint.GetParameters
title: IDebugBreakpoint::GetParameters (dbgeng.h)
description: The GetParameters method returns the parameters for a breakpoint.
old-location: debugger\getparameters.htm
tech.root: debugger
ms.assetid: 6b0e2a3d-2a62-4a79-a4e1-03168277caec
ms.date: 05/03/2018
ms.keywords: ComOther_1e2f7a47-0f38-492a-a8b2-9eaa124a2f20.xml, GetParameters, GetParameters method [Windows Debugging], GetParameters method [Windows Debugging],IDebugBreakpoint interface, GetParameters method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetParameters method, IDebugBreakpoint.GetParameters, IDebugBreakpoint2 interface [Windows Debugging],GetParameters method, IDebugBreakpoint2::GetParameters, IDebugBreakpoint::GetParameters, dbgeng/IDebugBreakpoint2::GetParameters, dbgeng/IDebugBreakpoint::GetParameters, debugger.getparameters
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
-	IDebugBreakpoint.GetParameters
-	IDebugBreakpoint2.GetParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint::GetParameters


## -description


The <b>GetParameters</b> method returns the parameters for a breakpoint.


## -parameters




### -param Params [out]

The breakpoint's parameters.  For more information about the parameters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541459">DEBUG_BREAKPOINT_PARAMETERS</a>.


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
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



The <b>GetParameters</b> method is a convenience method that returns most of the parameters that the other <a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a> methods return.

For a list of the parameters and flags that this method retrieves, and for other ways to read and write these parameters and flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.



