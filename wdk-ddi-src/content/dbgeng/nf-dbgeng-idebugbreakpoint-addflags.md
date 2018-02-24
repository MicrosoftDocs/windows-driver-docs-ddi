---
UID: NF:dbgeng.IDebugBreakpoint.AddFlags
title: IDebugBreakpoint::AddFlags method
author: windows-driver-content
description: The AddFlags method adds flags to a breakpoint.
old-location: debugger\addflags.htm
old-project: Debugger
ms.assetid: 92161111-5e02-4a97-9656-9a297e9ea1af
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: AddFlags, IDebugBreakpoint interface [Windows Debugging], AddFlags method, AddFlags method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint2 interface [Windows Debugging], AddFlags method, ComOther_2becec27-600b-4d57-93b0-8a794ff2f068.xml, debugger.addflags, AddFlags method [Windows Debugging], dbgeng/IDebugBreakpoint2::AddFlags, IDebugBreakpoint2::AddFlags, IDebugBreakpoint, AddFlags method [Windows Debugging], IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint::AddFlags, IDebugBreakpoint::AddFlags
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
-	Dbgeng.h
apiname:
-	IDebugBreakpoint.AddFlags
-	IDebugBreakpoint2.AddFlags
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint::AddFlags method


## -description


The <b>AddFlags</b> method adds flags to a <a href="https://msdn.microsoft.com/5ba110fc-1a12-4cbd-adc9-ef9441e257cb">breakpoint</a>.


## -syntax


````
HRESULT AddFlags(
  [in] ULONG Flags
);
````


## -parameters




### -param Flags [in]

Additional flags to add to the breakpoint.  <i>Flags</i> is a bit field that is combined together with the existing flags by using a bitwise OR.  For more information about the flag bit field and an explanation of each flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.  You cannot modify the DEBUG_BREAKPOINT_DEFERRED flag in the <a href="https://msdn.microsoft.com/1e32bd40-8c77-4c6b-913c-6ec26707ed36">engine</a>. This bit in <i>Flags</i> must always be zero.


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



For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



