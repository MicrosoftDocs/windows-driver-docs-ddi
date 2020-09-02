---
UID: NF:dbgeng.IDebugClient5.GetIdentityWide
title: IDebugClient5::GetIdentityWide (dbgeng.h)
description: The GetIdentityWide method returns a string describing the computer and user this client represents.
old-location: debugger\getidentitywide.htm
tech.root: debugger
ms.assetid: 8e55f829-2f55-4b83-8e0d-2554246a5d59
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetIdentityWide"]
ms.keywords: GetIdentityWide, GetIdentityWide method [Windows Debugging], GetIdentityWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetIdentityWide method, IDebugClient5.GetIdentityWide, IDebugClient5::GetIdentityWide, dbgeng/IDebugClient5::GetIdentityWide, debugger.getidentitywide
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
 - IDebugClient5::GetIdentityWide
 - dbgeng/IDebugClient5::GetIdentityWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.GetIdentityWide
---

# IDebugClient5::GetIdentityWide


## -description

The <b>GetIdentityWide</b> method returns a string describing the computer and user this client represents.

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

For more information about client objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">Client Objects</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-outputidentity">OutputIdentity</a>

