---
UID: NF:dbgeng.IDebugControl2.GetSystemErrorControl
title: IDebugControl2::GetSystemErrorControl method
author: windows-driver-content
description: The GetSystemErrorControl method returns the control values for handling system errors.
old-location: debugger\getsystemerrorcontrol.htm
old-project: debugger
ms.assetid: 727df033-ddaf-45a7-bdca-51a9ee0404fb
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, C, D, E, G, GetSystemErrorControl method [Windows Debugging], GetSystemErrorControl method [Windows Debugging], IDebugControl interface, GetSystemErrorControl method [Windows Debugging], IDebugControl2 interface, GetSystemErrorControl method [Windows Debugging], IDebugControl3 interface, GetSystemErrorControl,IDebugControl.GetSystemErrorControl, GetSystemErrorControl,IDebugControl2.GetSystemErrorControl, I, IDebugControl, IDebugControl interface [Windows Debugging], GetSystemErrorControl method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetSystemErrorControl method, IDebugControl2::GetSystemErrorControl, IDebugControl3 interface [Windows Debugging], GetSystemErrorControl method, IDebugControl3::GetSystemErrorControl, IDebugControl::GetSystemErrorControl, IDebugControl_94595f9e-7e73-4291-a904-49f1a8fbbaa8.xml, S, b, dbgeng/IDebugControl2::GetSystemErrorControl, dbgeng/IDebugControl3::GetSystemErrorControl, dbgeng/IDebugControl::GetSystemErrorControl, debugger.getsystemerrorcontrol, e, g, l, m, n, o, r, s, t, u, y"
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
-	IDebugControl.GetSystemErrorControl
-	IDebugControl2.GetSystemErrorControl
-	IDebugControl3.GetSystemErrorControl
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetSystemErrorControl method


## -description


The <b>GetSystemErrorControl</b> method returns the control values for handling system errors.


## -syntax


````
HRESULT GetSystemErrorControl(
  [out] PULONG OutputLevel,
  [out] PULONG BreakLevel
);
````


## -parameters




### -param OutputLevel [out]

Receives the level at which system errors are printed to the engine's output.  If the level of the system error is less than or equal to <i>OutputLevel</i>, the error is printed to the debugger console.


### -param BreakLevel [out]

Receives the level at which system errors break into the debugger.  If the level of the system error is less than or equal to <i>BreakLevel</i>, the error breaks into the debugger.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
 




## -remarks



The level of a system error can take one of the following three values, listed from lowest to highest: SLE_ERROR, SLE_MINORERROR, and SLE_WARNING.  These values are defined in Winuser.h.

When a system error occurs, the engine calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550768">IDebugEventCallbacks::SystemError</a> method of the event callbacks.  If the level is less than or equal to <i>BreakLevel</i>, the error will break into the debugger.  If the level is greater than <i>BreakLevel</i>, the engine will proceed with execution in the target as indicated by the <b>IDebugEventCallbacks::SystemError</b> method calls.  For more information about how the engine proceeds after an event, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556806">SetSystemErrorControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550768">IDebugEventCallbacks::SystemError</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetSystemErrorControl method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

