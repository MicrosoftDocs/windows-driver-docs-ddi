---
UID: NF:dbgeng.IDebugBreakpoint.SetOffsetExpression
title: IDebugBreakpoint::SetOffsetExpression method
author: windows-driver-content
description: The SetOffsetExpression methods set an expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\setoffsetexpression.htm
old-project: debugger
ms.assetid: 63cfb3f2-5240-4cb6-9c23-8cdb363f62a8
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetOffsetExpression, IDebugBreakpoint interface [Windows Debugging], SetOffsetExpression method, dbgeng/IDebugBreakpoint::SetOffsetExpression, IDebugBreakpoint2::SetOffsetExpression, IDebugBreakpoint, ComOther_d34036ae-b160-4b24-86d0-ebd2bd8408ea.xml, SetOffsetExpression method [Windows Debugging], IDebugBreakpoint interface, debugger.setoffsetexpression, SetOffsetExpression method [Windows Debugging], SetOffsetExpression method [Windows Debugging], IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetOffsetExpression, IDebugBreakpoint2 interface [Windows Debugging], SetOffsetExpression method, IDebugBreakpoint::SetOffsetExpression
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
-	IDebugBreakpoint.SetOffsetExpression
-	IDebugBreakpoint2.SetOffsetExpression
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugBreakpoint::SetOffsetExpression method


## -description


The <b>SetOffsetExpression</b>  methods set an expression string that evaluates to the location that triggers a breakpoint.


## -syntax


````
HRESULT SetOffsetExpression(
  [in] PCSTR Expression
);
````


## -parameters




### -param Expression [in]

The expression string that evaluates to the location on the target that triggers the breakpoint.  If the engine icannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.)  For more information about the expression syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.


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



For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.



