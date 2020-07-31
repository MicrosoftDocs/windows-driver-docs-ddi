---
UID: NF:dbgeng.IDebugClient.DispatchCallbacks
title: IDebugClient::DispatchCallbacks (dbgeng.h)
description: The DispatchCallbacks method lets the debugger engine use the current thread for callbacks.
old-location: debugger\dispatchcallbacks.htm
tech.root: debugger
ms.assetid: 05fb9569-c2d6-4650-b1c3-8b86ed7ef07d
ms.date: 05/03/2018
keywords: ["IDebugClient::DispatchCallbacks"]
ms.keywords: DispatchCallbacks, DispatchCallbacks method [Windows Debugging], DispatchCallbacks method [Windows Debugging],IDebugClient interface, DispatchCallbacks method [Windows Debugging],IDebugClient2 interface, DispatchCallbacks method [Windows Debugging],IDebugClient3 interface, DispatchCallbacks method [Windows Debugging],IDebugClient4 interface, DispatchCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],DispatchCallbacks method, IDebugClient.DispatchCallbacks, IDebugClient2 interface [Windows Debugging],DispatchCallbacks method, IDebugClient2::DispatchCallbacks, IDebugClient3 interface [Windows Debugging],DispatchCallbacks method, IDebugClient3::DispatchCallbacks, IDebugClient4 interface [Windows Debugging],DispatchCallbacks method, IDebugClient4::DispatchCallbacks, IDebugClient5 interface [Windows Debugging],DispatchCallbacks method, IDebugClient5::DispatchCallbacks, IDebugClient::DispatchCallbacks, IDebugClient_faf284c2-ca0f-4e00-bd74-08817338a808.xml, dbgeng/IDebugClient2::DispatchCallbacks, dbgeng/IDebugClient3::DispatchCallbacks, dbgeng/IDebugClient4::DispatchCallbacks, dbgeng/IDebugClient5::DispatchCallbacks, dbgeng/IDebugClient::DispatchCallbacks, debugger.dispatchcallbacks
f1_keywords:
 - "dbgeng/IDebugClient.DispatchCallbacks"
 - "IDebugClient.DispatchCallbacks"
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winbase.h
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
- IDebugClient.DispatchCallbacks
- IDebugClient2.DispatchCallbacks
- IDebugClient3.DispatchCallbacks
- IDebugClient4.DispatchCallbacks
- IDebugClient5.DispatchCallbacks
targetos: Windows
req.typenames: 
---

# IDebugClient::DispatchCallbacks


## -description


The <b>DispatchCallbacks</b> method lets the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> use the current thread for callbacks.


## -parameters




### -param Timeout [in]

Specifies how many milliseconds to wait before this method will return.  If <i>Timeout</i> is INFINITE, this method will not return until <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-exitdispatch">ExitDispatch</a> is called or an error occurs.


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
The method was successful (<b>ExitDispatch</b> was used).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
<i>Timeout</i> milliseconds elapsed.

</td>
</tr>
</table>
 




## -remarks



This method returns when <i>Timeout</i> milliseconds have elapsed, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-exitdispatch">ExitDispatch</a> is called, or an error occurs.

Almost all client methods must be called from the thread in which the client was created; <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/callback-objects">callback objects</a> registered with the client are also called from this thread.  When <b>DispatchCallbacks</b> is called the engine can use the current thread to make callback calls.

Client threads should call this method whenever possible to allow the callbacks to be called, unless the thread was the same thread used to start the debugger session, in which case the callbacks are called when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> is called.

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-exitdispatch">ExitDispatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-flushcallbacks">FlushCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a>
 

 

