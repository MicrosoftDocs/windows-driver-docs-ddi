---
UID: NF:dbgeng.IDebugClient5.GetOutputCallbacksWide
title: IDebugClient5::GetOutputCallbacksWide (dbgeng.h)
description: The GetOutputCallbacksWide method returns the output callbacks object registered with the client.
old-location: debugger\getoutputcallbackswide.htm
tech.root: debugger
ms.assetid: b93f756b-50b1-450f-8d70-5d1633b61fcf
ms.date: 05/03/2018
ms.keywords: GetOutputCallbacksWide, GetOutputCallbacksWide method [Windows Debugging], GetOutputCallbacksWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetOutputCallbacksWide method, IDebugClient5.GetOutputCallbacksWide, IDebugClient5::GetOutputCallbacksWide, dbgeng/IDebugClient5::GetOutputCallbacksWide, debugger.getoutputcallbackswide
f1_keywords:
 - "dbgeng/IDebugClient5.GetOutputCallbacksWide"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient5.GetOutputCallbacksWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetOutputCallbacksWide


## -description


The <b>GetOutputCallbacksWide</b> method returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a> object registered with the client.


## -parameters




### -param Callbacks [out]

Receives an interface pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> object registered with the client.


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



Each client can have at most one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

If no output callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugOutputCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugOutputCallbacksWide</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called.

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a>
 

 

