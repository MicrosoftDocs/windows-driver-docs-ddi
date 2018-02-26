---
UID: NF:dbgeng.IDebugBreakpoint2.GetCommandWide
title: IDebugBreakpoint2::GetCommandWide method
author: windows-driver-content
description: The GetCommand method returns the command string that is executed when a breakpoint is triggered.
old-location: debugger\getcommandwide.htm
old-project: debugger
ms.assetid: 050a4243-6ad8-4aa4-8ffb-40fe9fc07b51
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, B, C, D, G, GetCommandWide method [Windows Debugging], GetCommandWide method [Windows Debugging], IDebugBreakpoint2 interface, GetCommandWide,IDebugBreakpoint2.GetCommandWide, I, IDebugBreakpoint2, IDebugBreakpoint2 interface [Windows Debugging], GetCommandWide method, IDebugBreakpoint2::GetCommandWide, W, a, b, d, dbgeng/IDebugBreakpoint2::GetCommandWide, debugger.getcommandwide, e, g, i, k, m, n, o, p, r, t, u"
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
-	IDebugBreakpoint2.GetCommandWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint2::GetCommandWide method


## -description


The <b>GetCommand</b>  method returns the command string that is executed when a breakpoint is triggered.


## -syntax


````
HRESULT GetCommandWide(
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````


## -parameters




### -param Buffer [out, optional]

The command string that is executed when the breakpoint is triggered.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size, in characters, of the buffer that <i>Buffer</i> points to.


### -param CommandSize [out, optional]

The size of the command string.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful, but the buffer was not large enough to hold the command string and so the command string was truncated to fit.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the size of the breakpoint's command, <i>CommandSize</i>.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



