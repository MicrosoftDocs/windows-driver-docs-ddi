---
UID: NF:dbgeng.IDebugClient5.OutputServersWide
title: IDebugClient5::OutputServersWide method
author: windows-driver-content
description: The OutputServersWide method lists the servers running on a given computer.
old-location: debugger\outputserverswide.htm
old-project: debugger
ms.assetid: ce4b52af-17c6-41ed-95cb-09418137f049
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::OutputServersWide, OutputServersWide
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
req.alt-api: IDebugClient5.OutputServersWide
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugClient5::OutputServersWide method



## -description
The <b>OutputServersWide</b> method lists the servers running on a given computer.



## -syntax

````
HRESULT OutputServersWide(
  [in] ULONG  OutputControl,
  [in] PCWSTR Machine,
  [in] ULONG  Flags
);
````


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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about remote debugging, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554401">Remote Debugging</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558813">StartServer</a>
</dt>
<dt>
<a href="..\dbgeng\nf-dbgeng-debugconnect.md">DebugConnect</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::OutputServersWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

