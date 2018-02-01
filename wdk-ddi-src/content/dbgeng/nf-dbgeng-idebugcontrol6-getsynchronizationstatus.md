---
UID: NF:dbgeng.IDebugControl6.GetSynchronizationStatus
title: IDebugControl6::GetSynchronizationStatus method
author: windows-driver-content
description: The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.
old-location: debugger\idebugcontrol6_getsynchronizationstatus.htm
old-project: debugger
ms.assetid: 94DD7FBF-2D4F-4DD9-A49E-A9FA494BF995
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSynchronizationStatus method [Windows Debugging], debugger.idebugcontrol6_getsynchronizationstatus, dbgeng/IDebugControl6::GetSynchronizationStatus, IDebugControl6::GetSynchronizationStatus, GetSynchronizationStatus, IDebugControl6 interface [Windows Debugging], GetSynchronizationStatus method, GetSynchronizationStatus method [Windows Debugging], IDebugControl6 interface, IDebugControl6
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
-	IDebugControl6.GetSynchronizationStatus
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl6::GetSynchronizationStatus method


## -description


The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.


## -syntax


````
HRESULT GetSynchronizationStatus(
  [out] PULONG SendsAttempted,
  [out] PULONG SecondsSinceLastResponse
);
````


## -parameters




### -param SendsAttempted [out]

The number of packet sends that have been attempted by the current debugger-engine kernel transport mechanism. This number will be incremented if engine did not receive a packet "ACK" for the last packet sent by the engine to the target.


### -param SecondsSinceLastResponse [out]

The number of seconds since the last response.


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


When the client object connects to a session, the most recent output from the session is sent to the client. If the session is currently waiting on input, the client object is given the opportunity to provide input. Thus, the client object synchronizes with the session's input and output.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol6.md">IDebugControl6</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558852">Synchronizing with the Target Computer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl6::GetSynchronizationStatus method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

