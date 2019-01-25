---
UID: NF:dbgeng.IDebugBreakpoint.GetFlags
title: IDebugBreakpoint::GetFlags (dbgeng.h)
description: The GetFlags method returns the flags for a breakpoint.
old-location: debugger\getflags.htm
tech.root: debugger
ms.assetid: 0137a872-63e9-4630-86fa-accfaa9b6d6b
ms.date: 05/03/2018
ms.keywords: ComOther_5898a703-87fb-4d47-9d06-026783243e10.xml, GetFlags, GetFlags method [Windows Debugging], GetFlags method [Windows Debugging],IDebugBreakpoint interface, GetFlags method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetFlags method, IDebugBreakpoint.GetFlags, IDebugBreakpoint2 interface [Windows Debugging],GetFlags method, IDebugBreakpoint2::GetFlags, IDebugBreakpoint::GetFlags, dbgeng/IDebugBreakpoint2::GetFlags, dbgeng/IDebugBreakpoint::GetFlags, debugger.getflags
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
-	IDebugBreakpoint.GetFlags
-	IDebugBreakpoint2.GetFlags
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint::GetFlags


## -description


The <b>GetFlags</b> method returns the flags for a breakpoint.


## -parameters




### -param Flags [out]

The breakpoint's flags.  For more information about the flag bit field and an explanation of each flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.


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



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the breakpoint's flags.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



