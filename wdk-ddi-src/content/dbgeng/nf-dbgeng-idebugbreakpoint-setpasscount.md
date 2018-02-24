---
UID: NF:dbgeng.IDebugBreakpoint.SetPassCount
title: IDebugBreakpoint::SetPassCount method
author: windows-driver-content
description: The SetPassCount method sets the number of times that the target must reach the breakpoint location before the breakpoint is triggered.
old-location: debugger\setpasscount.htm
old-project: Debugger
ms.assetid: a95f7a8d-7e0d-4971-9683-f83600030337
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.setpasscount, IDebugBreakpoint interface [Windows Debugging], SetPassCount method, SetPassCount, SetPassCount method [Windows Debugging], IDebugBreakpoint interface, dbgeng/IDebugBreakpoint::SetPassCount, IDebugBreakpoint2 interface [Windows Debugging], SetPassCount method, IDebugBreakpoint2::SetPassCount, ComOther_8398fd11-1821-4adb-b8be-4e207b616169.xml, IDebugBreakpoint::SetPassCount, IDebugBreakpoint, dbgeng/IDebugBreakpoint2::SetPassCount, SetPassCount method [Windows Debugging], SetPassCount method [Windows Debugging], IDebugBreakpoint2 interface
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
-	IDebugBreakpoint.SetPassCount
-	IDebugBreakpoint2.SetPassCount
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint::SetPassCount method


## -description


The <b>SetPassCount</b> method sets the number of times that the target must reach the breakpoint location before the breakpoint is triggered.


## -syntax


````
HRESULT SetPassCount(
  [in] ULONG Count
);
````


## -parameters




### -param Count [in]

The number of times that the target must hit the breakpoint before it is triggered.  The number of times the target must pass the breakpoint without triggering it is the value of <i>Count</i>, minus one.


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



Every time that the <b>SetPassCount</b> method is called, the number of times that the target must reach the breakpoint location before the breakpoint is triggered is reset.

After the target has hit the breakpoint enough times to trigger the breakpoint, the breakpoint is triggered every time that it is hit, unless <b>SetPassCount</b> is called again.

If the debugger executes the code at the breakpoint location while stepping through the code, this execution does not contribute to the number of times that remain before the breakpoint is triggered.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



