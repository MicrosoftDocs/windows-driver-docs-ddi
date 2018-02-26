---
UID: NF:dbgeng.IDebugBreakpoint2.GetOffsetExpressionWide
title: IDebugBreakpoint2::GetOffsetExpressionWide method
author: windows-driver-content
description: The GetOffsetExpressionWide method returns the expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\getoffsetexpressionwide.htm
old-project: debugger
ms.assetid: bd4b32b1-e8ba-485f-bfb6-15c8c44926af
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, B, D, E, G, GetOffsetExpressionWide method [Windows Debugging], GetOffsetExpressionWide method [Windows Debugging], IDebugBreakpoint2 interface, GetOffsetExpressionWide,IDebugBreakpoint2.GetOffsetExpressionWide, I, IDebugBreakpoint2, IDebugBreakpoint2 interface [Windows Debugging], GetOffsetExpressionWide method, IDebugBreakpoint2::GetOffsetExpressionWide, O, W, a, b, d, dbgeng/IDebugBreakpoint2::GetOffsetExpressionWide, debugger.getoffsetexpressionwide, e, f, g, i, k, n, o, p, r, s, t, u, x"
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
-	IDebugBreakpoint2.GetOffsetExpressionWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint2::GetOffsetExpressionWide method


## -description


The <b>GetOffsetExpressionWide</b> method returns the expression string that evaluates to the location that triggers a breakpoint.


## -syntax


````
HRESULT GetOffsetExpressionWide(
  [out, optional] PWSTR  Buffer,
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



