---
UID: NF:dbgeng.IDebugClient5.DispatchCallbacks
title: IDebugClient5::DispatchCallbacks method
author: windows-driver-content
description: The DispatchCallbacks method lets the debugger engine use the current thread for callbacks.
old-location: debugger\dispatchcallbacks.htm
old-project: debugger
ms.assetid: 05fb9569-c2d6-4650-b1c3-8b86ed7ef07d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::DispatchCallbacks, DispatchCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winbase.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient.DispatchCallbacks,IDebugClient2.DispatchCallbacks,IDebugClient3.DispatchCallbacks,IDebugClient4.DispatchCallbacks,IDebugClient5.DispatchCallbacks
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugClient5::DispatchCallbacks method



## -description
The <b>DispatchCallbacks</b> method lets the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> use the current thread for callbacks.



## -syntax

````
HRESULT DispatchCallbacks(
  [in] ULONG Timeout
);
````


## -parameters

### -param Timeout [in]

Specifies how many milliseconds to wait before this method will return.  If <i>Timeout</i> is INFINITE, this method will not return until <a href="https://msdn.microsoft.com/library/windows/hardware/ff543265">ExitDispatch</a> is called or an error occurs.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful (<b>ExitDispatch</b> was used).
<dl>
<dt><b>S_FALSE</b></dt>
</dl><i>Timeout</i> milliseconds elapsed.

 


## -remarks
This method returns when <i>Timeout</i> milliseconds have elapsed, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543265">ExitDispatch</a> is called, or an error occurs.

Almost all client methods must be called from the thread in which the client was created; <a href="debugger.client_objects#callback_objects#callback_objects">callback objects</a> registered with the client are also called from this thread.  When <b>DispatchCallbacks</b> is called the engine can use the current thread to make callback calls.

Client threads should call this method whenever possible to allow the callbacks to be called, unless the thread was the same thread used to start the debugger session, in which case the callbacks are called when <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> is called.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543265">ExitDispatch</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545475">FlushCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::DispatchCallbacks method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

