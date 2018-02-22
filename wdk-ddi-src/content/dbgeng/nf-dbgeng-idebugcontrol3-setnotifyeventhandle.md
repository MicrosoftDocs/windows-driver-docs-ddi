---
UID: NF:dbgeng.IDebugControl3.SetNotifyEventHandle
title: IDebugControl3::SetNotifyEventHandle method
author: windows-driver-content
description: The SetNotifyEventHandle method sets the event that will be signaled after the next exception in a target.
old-location: debugger\setnotifyeventhandle.htm
old-project: Debugger
ms.assetid: 0c0059a7-4b0f-4b74-b543-ad5904d40033
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.setnotifyeventhandle, IDebugControl2, dbgeng/IDebugControl::SetNotifyEventHandle, dbgeng/IDebugControl3::SetNotifyEventHandle, IDebugControl, IDebugControl3, SetNotifyEventHandle method [Windows Debugging], IDebugControl interface, SetNotifyEventHandle method [Windows Debugging], IDebugControl3 interface [Windows Debugging], SetNotifyEventHandle method, dbgeng/IDebugControl2::SetNotifyEventHandle, IDebugControl2 interface [Windows Debugging], SetNotifyEventHandle method, IDebugControl2::SetNotifyEventHandle, IDebugControl interface [Windows Debugging], SetNotifyEventHandle method, IDebugControl::SetNotifyEventHandle, SetNotifyEventHandle method [Windows Debugging], IDebugControl2 interface, IDebugControl3::SetNotifyEventHandle, SetNotifyEventHandle method [Windows Debugging], IDebugControl3 interface, IDebugControl_9934efa7-aed4-4706-8885-71d78f6950a8.xml, SetNotifyEventHandle
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
-	IDebugControl.SetNotifyEventHandle
-	IDebugControl2.SetNotifyEventHandle
-	IDebugControl3.SetNotifyEventHandle
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetNotifyEventHandle method


## -description


The <b>SetNotifyEventHandle</b> method sets the event that will be signaled after the next <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a> in a target.


## -syntax


````
HRESULT SetNotifyEventHandle(
  [in] ULONG64 Handle
);
````


## -parameters




### -param Handle [in]

Specifies the handle of the event to signal.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.


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



After setting the event to signal, and after the next exception occurs in a target, when the engine resumes execution in the target, the event will be signaled.

The event will only be signaled once.  After it has been signaled, <b>GetNotifyEventHandle</b> will return <b>NULL</b>, unless this method is called to set another event to signal.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556739">SetNotifyEventHandle</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::SetNotifyEventHandle method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

