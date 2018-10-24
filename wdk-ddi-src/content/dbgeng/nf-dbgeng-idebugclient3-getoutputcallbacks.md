---
UID: NF:dbgeng.IDebugClient3.GetOutputCallbacks
title: IDebugClient3::GetOutputCallbacks
author: windows-driver-content
description: The GetOutputCallbacks method returns the output callbacks object registered with the client.
old-location: debugger\getoutputcallbacks.htm
tech.root: debugger
ms.assetid: 43f27e56-a6aa-4548-9c96-000e53a7eb9a
ms.date: 05/03/2018
ms.keywords: GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], GetOutputCallbacks method [Windows Debugging],IDebugClient interface, GetOutputCallbacks method [Windows Debugging],IDebugClient2 interface, GetOutputCallbacks method [Windows Debugging],IDebugClient3 interface, GetOutputCallbacks method [Windows Debugging],IDebugClient4 interface, GetOutputCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetOutputCallbacks method, IDebugClient2 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient2::GetOutputCallbacks, IDebugClient3 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient3.GetOutputCallbacks, IDebugClient3::GetOutputCallbacks, IDebugClient4 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient4::GetOutputCallbacks, IDebugClient5 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient5::GetOutputCallbacks, IDebugClient::GetOutputCallbacks, IDebugClient_693aaf2a-8408-48c4-b7c0-66e7064a6f35.xml, dbgeng/IDebugClient2::GetOutputCallbacks, dbgeng/IDebugClient3::GetOutputCallbacks, dbgeng/IDebugClient4::GetOutputCallbacks, dbgeng/IDebugClient5::GetOutputCallbacks, dbgeng/IDebugClient::GetOutputCallbacks, debugger.getoutputcallbacks
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
-	IDebugClient.GetOutputCallbacks
-	IDebugClient2.GetOutputCallbacks
-	IDebugClient3.GetOutputCallbacks
-	IDebugClient4.GetOutputCallbacks
-	IDebugClient5.GetOutputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::GetOutputCallbacks


## -description


The <b>GetOutputCallbacks</b> method returns the <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> object registered with the client.


## -parameters




### -param Callbacks [out]

Receives an interface pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a> object registered with the client.


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



Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

If no output callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugOutputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugOutputCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>
 

 

