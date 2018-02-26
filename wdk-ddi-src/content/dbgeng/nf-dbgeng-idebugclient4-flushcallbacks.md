---
UID: NF:dbgeng.IDebugClient4.FlushCallbacks
title: IDebugClient4::FlushCallbacks method
author: windows-driver-content
description: The FlushCallbacks method forces any remaining buffered output to be delivered to the IDebugOutputCallbacks object registered with this client.
old-location: debugger\flushcallbacks.htm
old-project: debugger
ms.assetid: 2ca4ea3b-befd-424d-a4a8-81436d0ffc1c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 4, :, C, D, F, FlushCallbacks method [Windows Debugging], FlushCallbacks method [Windows Debugging], IDebugClient interface, FlushCallbacks method [Windows Debugging], IDebugClient2 interface, FlushCallbacks method [Windows Debugging], IDebugClient3 interface, FlushCallbacks method [Windows Debugging], IDebugClient4 interface, FlushCallbacks method [Windows Debugging], IDebugClient5 interface, FlushCallbacks,IDebugClient.FlushCallbacks, FlushCallbacks,IDebugClient2.FlushCallbacks, FlushCallbacks,IDebugClient3.FlushCallbacks, FlushCallbacks,IDebugClient4.FlushCallbacks, I, IDebugClient, IDebugClient interface [Windows Debugging], FlushCallbacks method, IDebugClient2, IDebugClient2 interface [Windows Debugging], FlushCallbacks method, IDebugClient2::FlushCallbacks, IDebugClient3, IDebugClient3 interface [Windows Debugging], FlushCallbacks method, IDebugClient3::FlushCallbacks, IDebugClient4, IDebugClient4 interface [Windows Debugging], FlushCallbacks method, IDebugClient4::FlushCallbacks, IDebugClient5 interface [Windows Debugging], FlushCallbacks method, IDebugClient5::FlushCallbacks, IDebugClient::FlushCallbacks, IDebugClient_e808ca3a-5762-419b-96de-4c49984c1ccd.xml, a, b, c, dbgeng/IDebugClient2::FlushCallbacks, dbgeng/IDebugClient3::FlushCallbacks, dbgeng/IDebugClient4::FlushCallbacks, dbgeng/IDebugClient5::FlushCallbacks, dbgeng/IDebugClient::FlushCallbacks, debugger.flushcallbacks, e, g, h, i, k, l, n, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugClient.FlushCallbacks
-	IDebugClient2.FlushCallbacks
-	IDebugClient3.FlushCallbacks
-	IDebugClient4.FlushCallbacks
-	IDebugClient5.FlushCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::FlushCallbacks method


## -description


The <b>FlushCallbacks</b> method forces any remaining buffered output to be delivered to the <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a> object registered with this client. 


## -syntax


````
HRESULT FlushCallbacks();
````


## -parameters






## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



The engine sometimes merges compatible callback requests to reduce callback overhead; small pieces of output are collected into larger groups to reduce the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550815">IDebugOutputCallbacks::Output</a> calls.  Using <b>FlushCallbacks</b> is necessary for a client to guarantee that all pending callbacks have been processed at a particular point.  For example, a caller can flush callbacks before starting a lengthy operation outside of the engine so that pending callbacks are not delayed until after the operation.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550815">IDebugOutputCallbacks::Output</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::FlushCallbacks method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

