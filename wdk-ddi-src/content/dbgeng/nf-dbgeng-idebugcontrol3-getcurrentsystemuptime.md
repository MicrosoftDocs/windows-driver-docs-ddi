---
UID: NF:dbgeng.IDebugControl3.GetCurrentSystemUpTime
title: IDebugControl3::GetCurrentSystemUpTime method
author: windows-driver-content
description: The GetCurrentSystemUpTime method returns the number of seconds the current target's computer has been running since it was last started.
old-location: debugger\getcurrentsystemuptime.htm
old-project: debugger
ms.assetid: 0009e11d-73d0-4ca2-afbc-5f2999e829ac
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCurrentSystemUpTime method [Windows Debugging], GetCurrentSystemUpTime method [Windows Debugging], IDebugControl2 interface, GetCurrentSystemUpTime method [Windows Debugging], IDebugControl3 interface, GetCurrentSystemUpTime,IDebugControl3.GetCurrentSystemUpTime, IDebugControl2 interface [Windows Debugging], GetCurrentSystemUpTime method, IDebugControl2::GetCurrentSystemUpTime, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetCurrentSystemUpTime method, IDebugControl3::GetCurrentSystemUpTime, IDebugControl_e10ddd31-60fe-4353-befe-45a04154615b.xml, dbgeng/IDebugControl2::GetCurrentSystemUpTime, dbgeng/IDebugControl3::GetCurrentSystemUpTime, debugger.getcurrentsystemuptime
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl2.GetCurrentSystemUpTime
-	IDebugControl3.GetCurrentSystemUpTime
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetCurrentSystemUpTime method


## -description


The <b>GetCurrentSystemUpTime</b> method returns the number of seconds the current target's computer has been running since it was last started.


## -syntax


````
HRESULT GetCurrentSystemUpTime(
  [out] PULONG UpTime
);
````


## -parameters




### -param UpTime [out]

Receives the number of seconds the computer has been running, or <b>0</b> if the engine is unable to determine the running time.


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
The value of the variable <i>UpTime</i> is either the desired information or is <b>0</b>.

</td>
</tr>
</table>
 




## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546553">GetCurrentTimeDate</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl2::GetCurrentSystemUpTime method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

