---
UID: NF:dbgeng.IDebugClient.CreateClient
title: IDebugClient::CreateClient method
author: windows-driver-content
description: The CreateClient method creates a new client object for the current thread.
old-location: debugger\createclient.htm
old-project: debugger
ms.assetid: 61733b3e-87e9-4bb1-bed0-44efeffd7e4f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: CreateClient method [Windows Debugging], CreateClient method [Windows Debugging], IDebugClient interface, CreateClient method [Windows Debugging], IDebugClient2 interface, CreateClient method [Windows Debugging], IDebugClient3 interface, CreateClient method [Windows Debugging], IDebugClient4 interface, CreateClient method [Windows Debugging], IDebugClient5 interface, CreateClient,IDebugClient.CreateClient, IDebugClient, IDebugClient interface [Windows Debugging], CreateClient method, IDebugClient2 interface [Windows Debugging], CreateClient method, IDebugClient2::CreateClient, IDebugClient3 interface [Windows Debugging], CreateClient method, IDebugClient3::CreateClient, IDebugClient4 interface [Windows Debugging], CreateClient method, IDebugClient4::CreateClient, IDebugClient5 interface [Windows Debugging], CreateClient method, IDebugClient5::CreateClient, IDebugClient::CreateClient, IDebugClient_baa33ba0-bc95-4bfb-b8bf-b91598833599.xml, dbgeng/IDebugClient2::CreateClient, dbgeng/IDebugClient3::CreateClient, dbgeng/IDebugClient4::CreateClient, dbgeng/IDebugClient5::CreateClient, dbgeng/IDebugClient::CreateClient, debugger.createclient
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
req.lib: 
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
-	IDebugClient.CreateClient
-	IDebugClient2.CreateClient
-	IDebugClient3.CreateClient
-	IDebugClient4.CreateClient
-	IDebugClient5.CreateClient
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::CreateClient method


## -description


The <b>CreateClient</b> method creates a new client object for the current thread.


## -parameters




### -param Client [out]

Receives an interface pointer for the new client.


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



This method creates a client that may be used in the current thread.

Clients are specific to the thread that created them.  Calls from other threads fail immediately.  The <b>CreateClient</b> method is a notable exception; it allows creation of a new client for a new thread. 

All callbacks for a client are made in the thread with which the client was created.

For more information about client objects and how they are used in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540469">DebugCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::CreateClient method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

