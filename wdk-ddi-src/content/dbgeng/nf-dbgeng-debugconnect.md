---
UID: NF:dbgeng.DebugConnect
title: DebugConnect function (dbgeng.h)
description: The DebugConnect function creates a new client object and returns an interface pointer to it. The client object will be connected to a remote host.
old-location: debugger\debugconnect.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["DebugConnect function"]
ms.keywords: ClientFns_7beeb350-b8bd-44ea-b5c9-ca0da15146ae.xml, DebugConnect, DebugConnect function [Windows Debugging], dbgeng/DebugConnect, debugger.debugconnect
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
 - DebugConnect
 - dbgeng/DebugConnect
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - dbgeng.dll
api_name:
 - DebugConnect
---

# DebugConnect function


## -description

The <b>DebugConnect</b> and <b>DebugConnectWide</b> functions create a new client object and return an interface pointer to it.  The client object will be connected to a remote host.

## -parameters

### -param RemoteOptions [in]


Specifies how the debugger engine will connect to the remote host.  These are the same options that get passed to the <b>-remote</b> option on the command line.  For details on the syntax of this string, see <a href="/windows-hardware/drivers/debugger/activating-a-debugging-client">Activating a Debugging Client</a>.

### -param InterfaceId [in]


Specifies the interface identifier (IID) of the desired debugger engine client interface.  This is the type of the interface that will be returned in <i>Interface</i>. For information about the interface identifier, see <a href="/windows-hardware/drivers/debugger/using-client-objects">Using Client Objects</a>.

### -param Interface [out]


Receives an interface pointer for the new client.  The type of this interface is specified by <i>InterfaceId</i>.

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

As with **IUnknown::QueryInterface**, when the returned interface is no longer needed, its **IUnknown::Release** method should be called.

You don't need to call **CoInitialize**, **CoInitializeEx**, or **OleInitialize** to use this function and interfaces obtained by it.

## -see-also

<a href="/windows-hardware/drivers/debugger/client-objects">Client Objects</a>



Process Server and Smart Client
