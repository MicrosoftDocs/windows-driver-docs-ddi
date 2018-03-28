---
UID: NF:dbgeng.IDebugClient2.ExitDispatch
title: IDebugClient2::ExitDispatch method
author: windows-driver-content
description: The ExitDispatch method causes the DispatchCallbacks method to return.
old-location: debugger\exitdispatch.htm
old-project: debugger
ms.assetid: c4db90d9-d6d3-4bab-ac3a-6b94b0818f53
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ExitDispatch method [Windows Debugging], ExitDispatch method [Windows Debugging], IDebugClient interface, ExitDispatch method [Windows Debugging], IDebugClient2 interface, ExitDispatch method [Windows Debugging], IDebugClient3 interface, ExitDispatch method [Windows Debugging], IDebugClient4 interface, ExitDispatch method [Windows Debugging], IDebugClient5 interface, ExitDispatch,IDebugClient2.ExitDispatch, IDebugClient interface [Windows Debugging], ExitDispatch method, IDebugClient2, IDebugClient2 interface [Windows Debugging], ExitDispatch method, IDebugClient2::ExitDispatch, IDebugClient3 interface [Windows Debugging], ExitDispatch method, IDebugClient3::ExitDispatch, IDebugClient4 interface [Windows Debugging], ExitDispatch method, IDebugClient4::ExitDispatch, IDebugClient5 interface [Windows Debugging], ExitDispatch method, IDebugClient5::ExitDispatch, IDebugClient::ExitDispatch, IDebugClient_5c4cc320-694e-481a-814d-a77653548f7d.xml, dbgeng/IDebugClient2::ExitDispatch, dbgeng/IDebugClient3::ExitDispatch, dbgeng/IDebugClient4::ExitDispatch, dbgeng/IDebugClient5::ExitDispatch, dbgeng/IDebugClient::ExitDispatch, debugger.exitdispatch
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.ExitDispatch
-	IDebugClient2.ExitDispatch
-	IDebugClient3.ExitDispatch
-	IDebugClient4.ExitDispatch
-	IDebugClient5.ExitDispatch
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient2::ExitDispatch method


## -description


The <b>ExitDispatch</b> method causes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a> method to return.


## -parameters




### -param Client [in]

Specifies the client whose <a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a> method should return.


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



This method is reentrant and may be called from any thread.

This method can be used to interrupt a thread waiting in <a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a>.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::ExitDispatch method%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

