---
UID: NF:dbgeng.IDebugClient5.StartServerWide
title: IDebugClient5::StartServerWide (dbgeng.h)
description: The StartServerWide method starts a debugging server.
old-location: debugger\startserverwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::StartServerWide"]
ms.keywords: IDebugClient5 interface [Windows Debugging],StartServerWide method, IDebugClient5.StartServerWide, IDebugClient5::StartServerWide, StartServerWide, StartServerWide method [Windows Debugging], StartServerWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::StartServerWide, debugger.startserverwide
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
 - IDebugClient5::StartServerWide
 - dbgeng/IDebugClient5::StartServerWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.StartServerWide
---

# IDebugClient5::StartServerWide


## -description

The <b>StartServerWide</b> method starts a debugging server.

## -parameters

### -param Options 

[in]
Specifies the connections options for this server.  These are the same options given to the <b>.server</b> debugger command or the WinDbg and CDB <b>-server</b> command-line option.  For details on the syntax of this string, see <a href="/windows-hardware/drivers/debugger/activating-a-debugging-server">Activating a Debugging Server</a>.

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

The server that is started will be accessible by other <a href="/windows-hardware/drivers/debugger/debuggers-in-the-debugging-tools-for-windows-package">debuggers</a> through the transport specified in the <i>Options</i> parameter.

For more information about debugging servers, see Debugging Server and Debugging Client.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-debugconnect">DebugConnect</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-outputservers">OutputServers</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>
