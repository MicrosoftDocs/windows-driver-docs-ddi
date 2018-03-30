---
UID: NF:dbgeng.IDebugClient5.EndProcessServer
title: IDebugClient5::EndProcessServer method
author: windows-driver-content
description: The EndProcessServer method requests that a process server be shut down.
old-location: debugger\endprocessserver.htm
old-project: debugger
ms.assetid: 45421556-6781-4ec4-9ee1-783df99437ae
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EndProcessServer method [Windows Debugging], EndProcessServer method [Windows Debugging], IDebugClient2 interface, EndProcessServer method [Windows Debugging], IDebugClient3 interface, EndProcessServer method [Windows Debugging], IDebugClient4 interface, EndProcessServer method [Windows Debugging], IDebugClient5 interface, EndProcessServer,IDebugClient5.EndProcessServer, IDebugClient2 interface [Windows Debugging], EndProcessServer method, IDebugClient2::EndProcessServer, IDebugClient3 interface [Windows Debugging], EndProcessServer method, IDebugClient3::EndProcessServer, IDebugClient4 interface [Windows Debugging], EndProcessServer method, IDebugClient4::EndProcessServer, IDebugClient5, IDebugClient5 interface [Windows Debugging], EndProcessServer method, IDebugClient5::EndProcessServer, IDebugClient_a24a3c82-f966-424c-a739-a775b45cb600.xml, dbgeng/IDebugClient2::EndProcessServer, dbgeng/IDebugClient3::EndProcessServer, dbgeng/IDebugClient4::EndProcessServer, dbgeng/IDebugClient5::EndProcessServer, debugger.endprocessserver
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
-	IDebugClient2.EndProcessServer
-	IDebugClient3.EndProcessServer
-	IDebugClient4.EndProcessServer
-	IDebugClient5.EndProcessServer
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::EndProcessServer method


## -description


The <b>EndProcessServer</b> method requests that a process server be shut down.


## -parameters




### -param Server [in]

Specifies the process server to shut down.  This handle must have been previously returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>.


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



For more information about process servers and remote debugging, see <a href="https://msdn.microsoft.com/ed7ea3dc-07d1-481c-90e0-7f0b0e77ad42">Process Servers, Kernel Connection Servers, and Smart Clients</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541969">DisconnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561230">WaitForProcessServerEnd</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient2::EndProcessServer method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
