---
UID: NF:dbgeng.IDebugClient5.GetIdentity
title: IDebugClient5::GetIdentity (dbgeng.h)
description: The GetIdentity method returns a string describing the computer and user this client represents.
old-location: debugger\getidentity.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetIdentity"]
ms.keywords: GetIdentity, GetIdentity method [Windows Debugging], GetIdentity method [Windows Debugging],IDebugClient interface, GetIdentity method [Windows Debugging],IDebugClient2 interface, GetIdentity method [Windows Debugging],IDebugClient3 interface, GetIdentity method [Windows Debugging],IDebugClient4 interface, GetIdentity method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetIdentity method, IDebugClient2 interface [Windows Debugging],GetIdentity method, IDebugClient2::GetIdentity, IDebugClient3 interface [Windows Debugging],GetIdentity method, IDebugClient3::GetIdentity, IDebugClient4 interface [Windows Debugging],GetIdentity method, IDebugClient4::GetIdentity, IDebugClient5 interface [Windows Debugging],GetIdentity method, IDebugClient5.GetIdentity, IDebugClient5::GetIdentity, IDebugClient::GetIdentity, IDebugClient_7c54bffa-5190-49f5-919d-16bfb851ae36.xml, dbgeng/IDebugClient2::GetIdentity, dbgeng/IDebugClient3::GetIdentity, dbgeng/IDebugClient4::GetIdentity, dbgeng/IDebugClient5::GetIdentity, dbgeng/IDebugClient::GetIdentity, debugger.getidentity
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
 - IDebugClient5::GetIdentity
 - dbgeng/IDebugClient5::GetIdentity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5::GetIdentity
---

# IDebugClient5::GetIdentity


## -description

The <b>GetIdentity</b>  method returns a string describing the computer and user this client represents.

## -parameters

### -param Buffer 

[out, optional]
Specifies the buffer to receive the string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size of the buffer <i>Buffer</i>.

### -param IdentitySize 

[out, optional]
Receives the size of the string. If <i>IdentitySize</i> is <b>NULL</b>, this information is not returned.

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
The method was successful

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.

</td>
</tr>
</table>

## -remarks

The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="/windows-hardware/drivers/debugger/client-objects">Client Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-outputidentity">OutputIdentity</a>

