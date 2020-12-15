---
UID: NF:dbgeng.IDebugClient5.OutputServersWide
title: IDebugClient5::OutputServersWide (dbgeng.h)
description: The OutputServersWide method lists the servers running on a given computer.
old-location: debugger\outputserverswide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::OutputServersWide"]
ms.keywords: IDebugClient5 interface [Windows Debugging],OutputServersWide method, IDebugClient5.OutputServersWide, IDebugClient5::OutputServersWide, OutputServersWide, OutputServersWide method [Windows Debugging], OutputServersWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::OutputServersWide, debugger.outputserverswide
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
 - IDebugClient5::OutputServersWide
 - dbgeng/IDebugClient5::OutputServersWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.OutputServersWide
---

# IDebugClient5::OutputServersWide


## -description

The <b>OutputServersWide</b> method lists the servers running on a given computer.

## -parameters

### -param OutputControl 

[in]
Specifies the output control to use while outputting the servers. For possible values, see <a href="/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.

### -param Machine 

[in]
Specifies the name of the computer whose servers will be listed.  <i>Machine</i> has the following form:

\\<i>computername</i>

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

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about remote debugging, see <a href="/windows-hardware/drivers/debugger/remote-debugging5">Remote Debugging</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-debugconnect">DebugConnect</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startserver">StartServer</a>
