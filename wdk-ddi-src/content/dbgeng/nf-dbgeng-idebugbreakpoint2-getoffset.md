---
UID: NF:dbgeng.IDebugBreakpoint2.GetOffset
title: IDebugBreakpoint2::GetOffset method
author: windows-driver-content
description: The GetOffset method returns the location that triggers a breakpoint.
old-location: debugger\getoffset.htm
old-project: debugger
ms.assetid: 7da401c9-10c1-4a2b-91ea-c0f9f58fd87a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getoffset, GetOffset method [Windows Debugging], IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint::GetOffset, ComOther_020a92c1-effa-4b14-9198-153641401e46.xml, GetOffset method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint2, IDebugBreakpoint2::GetOffset, IDebugBreakpoint2 interface [Windows Debugging], GetOffset method, dbgeng/IDebugBreakpoint2::GetOffset, GetOffset method [Windows Debugging], IDebugBreakpoint::GetOffset, GetOffset, IDebugBreakpoint interface [Windows Debugging], GetOffset method
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
-	IDebugBreakpoint.GetOffset
-	IDebugBreakpoint2.GetOffset
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugBreakpoint2::GetOffset method


## -description


The <b>GetOffset</b> method returns the location that triggers a breakpoint.


## -syntax


````
HRESULT GetOffset(
  [out] PULONG64 Offset
);
````


## -parameters




### -param Offset [out]

The location on the target that triggers the breakpoint.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint is deferred and does not currently specify a location in the target's memory address space. To determine the breakpoint location in this case, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548048">GetOffsetExpression</a>.

</td>
</tr>
</table> 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.



## -remarks


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the location that triggers a breakpoint.

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.


