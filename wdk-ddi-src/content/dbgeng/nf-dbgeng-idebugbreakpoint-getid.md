---
UID: NF:dbgeng.IDebugBreakpoint.GetId
title: IDebugBreakpoint::GetId method
author: windows-driver-content
description: The GetId method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.
old-location: debugger\getid.htm
old-project: debugger
ms.assetid: 991d8a40-1991-4c06-9557-9abee3ed8073
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_408e8e80-f34e-4895-9bae-66dbb0f9aa97.xml, GetId method [Windows Debugging], GetId method [Windows Debugging], IDebugBreakpoint interface, GetId method [Windows Debugging], IDebugBreakpoint2 interface, GetId,IDebugBreakpoint.GetId, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], GetId method, IDebugBreakpoint2 interface [Windows Debugging], GetId method, IDebugBreakpoint2::GetId, IDebugBreakpoint::GetId, dbgeng/IDebugBreakpoint2::GetId, dbgeng/IDebugBreakpoint::GetId, debugger.getid
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
-	IDebugBreakpoint.GetId
-	IDebugBreakpoint2.GetId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint::GetId method


## -description


The <b>GetId</b> method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.


## -syntax


````
HRESULT GetId(
  [out] PULONG Id
);
````


## -parameters




### -param Id [out]

The breakpoint ID.


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



The breakpoint ID remains fixed as long as the breakpoint exists.  However, after the breakpoint has been removed, you can use its ID for another breakpoint.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the breakpoint ID.

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.



