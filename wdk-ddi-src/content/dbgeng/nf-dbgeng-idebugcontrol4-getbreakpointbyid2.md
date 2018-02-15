---
UID: NF:dbgeng.IDebugControl4.GetBreakpointById2
title: IDebugControl4::GetBreakpointById2 method
author: windows-driver-content
description: The GetBreakpointById2 method returns the breakpoint with the specified breakpoint ID.
old-location: debugger\getbreakpointbyid2.htm
old-project: debugger
ms.assetid: 110eaa8a-d564-4900-8a08-d081572a5f43
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetBreakpointById2 method [Windows Debugging], IDebugControl4 interface [Windows Debugging], GetBreakpointById2 method, IDebugControl4::GetBreakpointById2, GetBreakpointById2, debugger.getbreakpointbyid2, dbgeng/IDebugControl4::GetBreakpointById2, IDebugControl4, GetBreakpointById2 method [Windows Debugging], IDebugControl4 interface
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
-	IDebugControl4.GetBreakpointById2
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl4::GetBreakpointById2 method


## -description


The <b>GetBreakpointById2</b>  method returns the breakpoint with the specified breakpoint ID.


## -syntax


````
HRESULT GetBreakpointById2(
  [in]  ULONG              Id,
  [out] PDEBUG_BREAKPOINT2 *Bp
);
````


## -parameters




### -param Id [in]

Specifies the breakpoint ID of the breakpoint to return.


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
No breakpoint was found with the given ID, or the breakpoint with the specified ID does not belong to the current process, or the breakpoint with the given ID is private (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546791">GetFlags</a>).

</td>
</tr>
</table>
 




## -remarks



If the specified breakpoint does not belong to the current process, the method will fail.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetBreakpointById2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

