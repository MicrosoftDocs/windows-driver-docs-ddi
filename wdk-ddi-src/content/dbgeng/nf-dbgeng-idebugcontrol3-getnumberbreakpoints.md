---
UID: NF:dbgeng.IDebugControl3.GetNumberBreakpoints
title: IDebugControl3::GetNumberBreakpoints method
author: windows-driver-content
description: The GetNumberBreakpoints method returns the number of breakpoints for the current process.
old-location: debugger\getnumberbreakpoints.htm
old-project: debugger
ms.assetid: 9faffb72-3559-4db7-a02e-3d93dc751ac3
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl3::GetNumberBreakpoints, GetNumberBreakpoints, GetNumberBreakpoints method [Windows Debugging], IDebugControl3, IDebugControl2 interface [Windows Debugging], GetNumberBreakpoints method, GetNumberBreakpoints method [Windows Debugging], IDebugControl interface, IDebugControl2::GetNumberBreakpoints, GetNumberBreakpoints method [Windows Debugging], IDebugControl2 interface, GetNumberBreakpoints method [Windows Debugging], IDebugControl3 interface, IDebugControl interface [Windows Debugging], GetNumberBreakpoints method, dbgeng/IDebugControl::GetNumberBreakpoints, IDebugControl3 interface [Windows Debugging], GetNumberBreakpoints method, IDebugControl_c5b9bf83-0a0e-4570-8a05-04ca39a4d335.xml, dbgeng/IDebugControl3::GetNumberBreakpoints, debugger.getnumberbreakpoints, IDebugControl::GetNumberBreakpoints, dbgeng/IDebugControl2::GetNumberBreakpoints
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
-	IDebugControl.GetNumberBreakpoints
-	IDebugControl2.GetNumberBreakpoints
-	IDebugControl3.GetNumberBreakpoints
product: Windows
targetos: Windows
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::GetNumberBreakpoints method


## -description


The <b>GetNumberBreakpoints</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">breakpoints</a> for the current process.


## -syntax


````
HRESULT GetNumberBreakpoints(
  [out] PULONG Number
);
````


## -parameters




### -param Number [out]

Receives the number of breakpoints.


## -returns


This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537856">AddBreakpoint</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetNumberBreakpoints method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

