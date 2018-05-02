---
UID: NF:dbgeng.IDebugClient5.OutputServersWide
title: IDebugClient5::OutputServersWide
author: windows-driver-content
description: The OutputServersWide method lists the servers running on a given computer.
old-location: debugger\outputserverswide.htm
old-project: debugger
ms.assetid: ce4b52af-17c6-41ed-95cb-09418137f049
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],OutputServersWide method, IDebugClient5.OutputServersWide, IDebugClient5::OutputServersWide, OutputServersWide, OutputServersWide method [Windows Debugging], OutputServersWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::OutputServersWide, debugger.outputserverswide
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
-	IDebugClient5.OutputServersWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::OutputServersWide


## -description


The <b>OutputServersWide</b> method lists the servers running on a given computer.


## -parameters




### -param OutputControl [in]

Specifies the output control to use while outputting the servers. For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Machine [in]

Specifies the name of the computer whose servers will be listed.  <i>Machine</i> has the following form:

\\<i>computername</i>


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558813">StartServer</a>
 

 

