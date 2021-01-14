---
UID: NF:dbgeng.IDebugClient5.SetOutputCallbacksWide
title: IDebugClient5::SetOutputCallbacksWide (dbgeng.h)
description: The SetOutputCallbacksWide method registers an output callbacks object with this client.
old-location: debugger\setoutputcallbackswide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::SetOutputCallbacksWide"]
ms.keywords: IDebugClient5 interface [Windows Debugging],SetOutputCallbacksWide method, IDebugClient5.SetOutputCallbacksWide, IDebugClient5::SetOutputCallbacksWide, SetOutputCallbacksWide, SetOutputCallbacksWide method [Windows Debugging], SetOutputCallbacksWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::SetOutputCallbacksWide, debugger.setoutputcallbackswide
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
 - IDebugClient5::SetOutputCallbacksWide
 - dbgeng/IDebugClient5::SetOutputCallbacksWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5::SetOutputCallbacksWide
---

# IDebugClient5::SetOutputCallbacksWide


## -description

The <b>SetOutputCallbacksWide</b> method registers an <a href="/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a> object with this client.

## -parameters

### -param Callbacks 

[in]
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

Each client can have at most one <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

The <b>IDebugOutputCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetOutputCallbacks</b> and <b>SetOutputCAllbacksWide</b> call the <b>IUnknown::AddRef</b> method in the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetOutputCallbacks</b> or <b>SetOutputCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getoutputcallbacks">GetOutputCallbacks</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>

