---
UID: NF:dbgeng.IDebugClient3.WaitForProcessServerEnd
title: IDebugClient3::WaitForProcessServerEnd (dbgeng.h)
description: The WaitForProcessServerEnd method waits for a local process server to exit.
old-location: debugger\waitforprocessserverend.htm
tech.root: debugger
ms.assetid: 19573307-0192-47bd-86a0-9c7721d16c5e
ms.date: 05/03/2018
ms.keywords: IDebugClient2 interface [Windows Debugging],WaitForProcessServerEnd method, IDebugClient2::WaitForProcessServerEnd, IDebugClient3 interface [Windows Debugging],WaitForProcessServerEnd method, IDebugClient3.WaitForProcessServerEnd, IDebugClient3::WaitForProcessServerEnd, IDebugClient4 interface [Windows Debugging],WaitForProcessServerEnd method, IDebugClient4::WaitForProcessServerEnd, IDebugClient5 interface [Windows Debugging],WaitForProcessServerEnd method, IDebugClient5::WaitForProcessServerEnd, IDebugClient_ac54327c-85c5-41ab-906f-605d374a0e2d.xml, WaitForProcessServerEnd, WaitForProcessServerEnd method [Windows Debugging], WaitForProcessServerEnd method [Windows Debugging],IDebugClient2 interface, WaitForProcessServerEnd method [Windows Debugging],IDebugClient3 interface, WaitForProcessServerEnd method [Windows Debugging],IDebugClient4 interface, WaitForProcessServerEnd method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::WaitForProcessServerEnd, dbgeng/IDebugClient3::WaitForProcessServerEnd, dbgeng/IDebugClient4::WaitForProcessServerEnd, dbgeng/IDebugClient5::WaitForProcessServerEnd, debugger.waitforprocessserverend
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winbase.h
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient2.WaitForProcessServerEnd
- IDebugClient3.WaitForProcessServerEnd
- IDebugClient4.WaitForProcessServerEnd
- IDebugClient5.WaitForProcessServerEnd
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::WaitForProcessServerEnd


## -description


The <b>WaitForProcessServerEnd</b> method waits for a local process server to exit.


## -parameters




### -param Timeout [in]

Specifies how long in milliseconds to wait for a process server to exit.  If <i>Timeout</i> is INFINITE, this method will not return until a process server has ended.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
A time-out occurred -- <i>Timeout</i> milliseconds passed without a local process server exiting.

</td>
</tr>
</table>
 




## -remarks



This method will only wait for the first local process server to end.  After a process server has ended, subsequent calls to this method will return immediately.

For more information about process servers and remote debugging, see <a href="https://msdn.microsoft.com/ed7ea3dc-07d1-481c-90e0-7f0b0e77ad42">Process Servers, Kernel Connection Servers, and Smart Clients</a>.

The constant INFINITE is defined in Winbase.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>
 

 

