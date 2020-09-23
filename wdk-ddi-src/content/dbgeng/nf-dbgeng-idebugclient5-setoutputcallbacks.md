---
UID: NF:dbgeng.IDebugClient5.SetOutputCallbacks
title: IDebugClient5::SetOutputCallbacks (dbgeng.h)
description: The SetOutputCallbacks method registers an output callbacks object with this client.
old-location: debugger\setoutputcallbacks.htm
tech.root: debugger
ms.assetid: 2226804c-dbdd-4855-9ba5-7c1959941e59
ms.date: 05/03/2018
keywords: ["IDebugClient5::SetOutputCallbacks"]
ms.keywords: IDebugClient interface [Windows Debugging],SetOutputCallbacks method, IDebugClient2 interface [Windows Debugging],SetOutputCallbacks method, IDebugClient2::SetOutputCallbacks, IDebugClient3 interface [Windows Debugging],SetOutputCallbacks method, IDebugClient3::SetOutputCallbacks, IDebugClient4 interface [Windows Debugging],SetOutputCallbacks method, IDebugClient4::SetOutputCallbacks, IDebugClient5 interface [Windows Debugging],SetOutputCallbacks method, IDebugClient5.SetOutputCallbacks, IDebugClient5::SetOutputCallbacks, IDebugClient::SetOutputCallbacks, IDebugClient_b1da4bc1-b368-475e-bd13-021358f9d234.xml, SetOutputCallbacks, SetOutputCallbacks method [Windows Debugging], SetOutputCallbacks method [Windows Debugging],IDebugClient interface, SetOutputCallbacks method [Windows Debugging],IDebugClient2 interface, SetOutputCallbacks method [Windows Debugging],IDebugClient3 interface, SetOutputCallbacks method [Windows Debugging],IDebugClient4 interface, SetOutputCallbacks method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetOutputCallbacks, dbgeng/IDebugClient3::SetOutputCallbacks, dbgeng/IDebugClient4::SetOutputCallbacks, dbgeng/IDebugClient5::SetOutputCallbacks, dbgeng/IDebugClient::SetOutputCallbacks, debugger.setoutputcallbacks
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
 - IDebugClient5::SetOutputCallbacks
 - dbgeng/IDebugClient5::SetOutputCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.SetOutputCallbacks
 - IDebugClient2.SetOutputCallbacks
 - IDebugClient3.SetOutputCallbacks
 - IDebugClient4.SetOutputCallbacks
 - IDebugClient5.SetOutputCallbacks
---

# IDebugClient5::SetOutputCallbacks


## -description

The <b>SetOutputCallbacks</b> method registers an <a href="/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a> object with this client.

## -parameters

### -param Callbacks 

[in, optional]
Specifies the interface pointer to the output callbacks object to register with this client.

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

Each client can have at most one <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacks</b> object registered with it for output.

The <b>IDebugOutputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetOutputCallbacks</b> and <b>SetOutputCAllbacksWide</b> call the <b>IUnknown::AddRef</b> method in the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetOutputCallbacks</b> or <b>SetOutputCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getoutputcallbacks">GetOutputCallbacks</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>