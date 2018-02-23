---
UID: NF:dbgeng.IDebugBreakpoint2.RemoveFlags
title: IDebugBreakpoint2::RemoveFlags method
author: windows-driver-content
description: The RemoveFlags method removes flags from a breakpoint.
old-location: debugger\removeflags.htm
old-project: Debugger
ms.assetid: 60538544-6baf-4d23-a65f-5c5e82bd6f11
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: dbgeng/IDebugBreakpoint::RemoveFlags, RemoveFlags, RemoveFlags method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint2::RemoveFlags, dbgeng/IDebugBreakpoint2::RemoveFlags, RemoveFlags method [Windows Debugging], IDebugBreakpoint2 interface, IDebugBreakpoint2, ComOther_15793582-5533-4f63-8278-9556b160e6d2.xml, IDebugBreakpoint::RemoveFlags, RemoveFlags method [Windows Debugging], debugger.removeflags, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], RemoveFlags method, IDebugBreakpoint2 interface [Windows Debugging], RemoveFlags method
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
-	IDebugBreakpoint.RemoveFlags
-	IDebugBreakpoint2.RemoveFlags
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint2::RemoveFlags method


## -description


The <b>RemoveFlags</b> method removes flags from a breakpoint.


## -syntax


````
HRESULT RemoveFlags(
  [in] ULONG Flags
);
````


## -parameters




### -param Flags [in]

Flags to remove from the breakpoint.  <i>Flags</i> is a bit field. The new value of the flags in the engine is the old value and not the value of <i>Flags</i>.  For more information about the flag bit field and an explanation of each flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.  You cannot modify the DEBUG_BREAKPOINT_DEFERRED flag in the engine. This bit in <i>Flags</i> must always be zero.


## -returns



<b>RemoveFlags</b> might return one of the following values:

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



For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



