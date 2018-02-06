---
UID: NF:dbgeng.IDebugBreakpoint2.GetOffsetExpression
title: IDebugBreakpoint2::GetOffsetExpression method
author: windows-driver-content
description: The GetOffsetExpression methods return the expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\getoffsetexpression.htm
old-project: debugger
ms.assetid: 9fbdfa42-7231-4281-ba19-a33e854cd801
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetOffsetExpression method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint2 interface [Windows Debugging], GetOffsetExpression method, IDebugBreakpoint::GetOffsetExpression, IDebugBreakpoint2, debugger.getoffsetexpression, GetOffsetExpression method [Windows Debugging], IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::GetOffsetExpression, GetOffsetExpression, dbgeng/IDebugBreakpoint::GetOffsetExpression, IDebugBreakpoint2::GetOffsetExpression, ComOther_08bb15b2-f37d-4bd2-b19a-899ab9293f4a.xml, GetOffsetExpression method [Windows Debugging], IDebugBreakpoint interface [Windows Debugging], GetOffsetExpression method
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
-	IDebugBreakpoint.GetOffsetExpression
-	IDebugBreakpoint2.GetOffsetExpression
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugBreakpoint2::GetOffsetExpression method


## -description


The <b>GetOffsetExpression</b>  methods return the expression string that evaluates to the location that triggers a breakpoint.


## -syntax


````
HRESULT GetOffsetExpression(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG ExpressionSize
);
````


## -parameters




### -param Buffer [out, optional]

The expression string that evaluates to the location on the target that triggers the breakpoint.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size, in characters, of the buffer that <i>Buffer </i>points to.


### -param ExpressionSize [out, optional]

The size, in characters, of the expression string.  If <i>ExpressionSize</i> is <b>NULL</b>, this information is not returned.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but the buffer was not large enough to hold the expression string and so the string was truncated to fit.

</td>
</tr>
</table> 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.



## -remarks


The expression is evaluated every time that a module is loaded or unloaded.  If the debugger cannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.)

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the size of the expression string that specifies the location that triggers the breakpoint, <i>ExpressionSize</i>.

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.


