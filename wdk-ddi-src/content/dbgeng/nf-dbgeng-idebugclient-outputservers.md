---
UID: NF:dbgeng.IDebugClient.OutputServers
title: IDebugClient::OutputServers (dbgeng.h)
description: The OutputServers method lists the servers running on a given computer.
old-location: debugger\outputservers.htm
tech.root: debugger
ms.assetid: cb08e0d9-8c4b-4b7f-be3d-4e7c87d7f3d4
ms.date: 05/03/2018
keywords: ["IDebugClient::OutputServers"]
ms.keywords: IDebugClient interface [Windows Debugging],OutputServers method, IDebugClient.OutputServers, IDebugClient2 interface [Windows Debugging],OutputServers method, IDebugClient2::OutputServers, IDebugClient3 interface [Windows Debugging],OutputServers method, IDebugClient3::OutputServers, IDebugClient4 interface [Windows Debugging],OutputServers method, IDebugClient4::OutputServers, IDebugClient5 interface [Windows Debugging],OutputServers method, IDebugClient5::OutputServers, IDebugClient::OutputServers, IDebugClient_8fecfb37-5e4d-4a2b-af1e-df081e636337.xml, OutputServers, OutputServers method [Windows Debugging], OutputServers method [Windows Debugging],IDebugClient interface, OutputServers method [Windows Debugging],IDebugClient2 interface, OutputServers method [Windows Debugging],IDebugClient3 interface, OutputServers method [Windows Debugging],IDebugClient4 interface, OutputServers method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::OutputServers, dbgeng/IDebugClient3::OutputServers, dbgeng/IDebugClient4::OutputServers, dbgeng/IDebugClient5::OutputServers, dbgeng/IDebugClient::OutputServers, debugger.outputservers
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugClient::OutputServers
 - dbgeng/IDebugClient::OutputServers
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.OutputServers
 - IDebugClient2.OutputServers
 - IDebugClient3.OutputServers
 - IDebugClient4.OutputServers
 - IDebugClient5.OutputServers
---

# IDebugClient::OutputServers


## -description

The <b>OutputServers</b>  method lists the servers running on a given computer.

## -parameters

### -param OutputControl 

[in]
Specifies the output control to use while outputting the servers. For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.

### -param Machine 

[in]
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

### -param Flags 

[in]
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

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about remote debugging, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/remote-debugging5">Remote Debugging</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-debugconnect">DebugConnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startserver">StartServer</a>

