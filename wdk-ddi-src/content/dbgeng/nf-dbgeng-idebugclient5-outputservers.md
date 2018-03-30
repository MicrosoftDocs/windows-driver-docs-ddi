---
UID: NF:dbgeng.IDebugClient5.OutputServers
title: IDebugClient5::OutputServers method
author: windows-driver-content
description: The OutputServers method lists the servers running on a given computer.
old-location: debugger\outputservers.htm
old-project: debugger
ms.assetid: cb08e0d9-8c4b-4b7f-be3d-4e7c87d7f3d4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient interface [Windows Debugging], OutputServers method, IDebugClient2 interface [Windows Debugging], OutputServers method, IDebugClient2::OutputServers, IDebugClient3 interface [Windows Debugging], OutputServers method, IDebugClient3::OutputServers, IDebugClient4 interface [Windows Debugging], OutputServers method, IDebugClient4::OutputServers, IDebugClient5, IDebugClient5 interface [Windows Debugging], OutputServers method, IDebugClient5::OutputServers, IDebugClient::OutputServers, IDebugClient_8fecfb37-5e4d-4a2b-af1e-df081e636337.xml, OutputServers method [Windows Debugging], OutputServers method [Windows Debugging], IDebugClient interface, OutputServers method [Windows Debugging], IDebugClient2 interface, OutputServers method [Windows Debugging], IDebugClient3 interface, OutputServers method [Windows Debugging], IDebugClient4 interface, OutputServers method [Windows Debugging], IDebugClient5 interface, OutputServers,IDebugClient5.OutputServers, dbgeng/IDebugClient2::OutputServers, dbgeng/IDebugClient3::OutputServers, dbgeng/IDebugClient4::OutputServers, dbgeng/IDebugClient5::OutputServers, dbgeng/IDebugClient::OutputServers, debugger.outputservers
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
-	IDebugClient.OutputServers
-	IDebugClient2.OutputServers
-	IDebugClient3.OutputServers
-	IDebugClient4.OutputServers
-	IDebugClient5.OutputServers
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::OutputServers method


## -description


The <b>OutputServers</b>  method lists the servers running on a given computer.


## -parameters




### -param OutputControl [in]

Specifies the output control to use while outputting the servers. For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Machine [in]

Specifies the name of the computer whose servers will be listed.  <i>Machine</i> has the following form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\\computername</pre>
</td>
</tr>
</table></span></div>

### -param Flags [in]

Specifies a bit-set that determines which servers to output.  The possible bit flags are:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_SERVERS_DEBUGGER

</td>
<td>
Output the debugging servers on the computer.

</td>
</tr>
<tr>
<td>
DEBUG_SERVERS_PROCESS

</td>
<td>
Output the process servers on the computer.

</td>
</tr>
</table>
 


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



For more information about remote debugging, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554401">Remote Debugging</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540465">DebugConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558813">StartServer</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::OutputServers method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
