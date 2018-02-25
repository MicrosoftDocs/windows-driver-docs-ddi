---
UID: NF:dbgeng.IDebugControl5.GetBreakpointByGuid
title: IDebugControl5::GetBreakpointByGuid method
author: windows-driver-content
description: The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.
old-location: debugger\idebugcontrol5_getbreakpointbyguid.htm
old-project: debugger
ms.assetid: AC316591-CCF9-4040-B1A3-29AB2033B673
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 5, :, B, C, D, G, GetBreakpointByGuid method [Windows Debugging], GetBreakpointByGuid method [Windows Debugging], IDebugControl5 interface, GetBreakpointByGuid,IDebugControl5.GetBreakpointByGuid, I, IDebugControl5, IDebugControl5 interface [Windows Debugging], GetBreakpointByGuid method, IDebugControl5::GetBreakpointByGuid, a, b, d, dbgeng/IDebugControl5::GetBreakpointByGuid, debugger.idebugcontrol5_getbreakpointbyguid, e, g, i, k, l, n, o, p, r, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
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
-	IDebugControl5.GetBreakpointByGuid
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl5::GetBreakpointByGuid method


## -description


The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.


## -syntax


````
HRESULT GetBreakpointByGuid(
  [in]  LPGUID             Guid,
  [out] PDEBUG_BREAKPOINT3 *Bp
);
````


## -parameters




### -param Guid [in]

Specifies the breakpoint GUID of the breakpoint to return.


### -param Bp [out]

Receives the breakpoint.


## -returns



This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
No breakpoint was found with the given GUID, or the breakpoint with the specified GUID does not belong to the current process, or the breakpoint with the given GUID is private (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546791">GetFlags</a>). 

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5::GetBreakpointByGuid method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

