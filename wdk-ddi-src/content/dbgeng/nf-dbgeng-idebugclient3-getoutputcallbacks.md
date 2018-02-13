---
UID: NF:dbgeng.IDebugClient3.GetOutputCallbacks
title: IDebugClient3::GetOutputCallbacks method
author: windows-driver-content
description: The GetOutputCallbacks method returns the output callbacks object registered with the client.
old-location: debugger\getoutputcallbacks.htm
old-project: debugger
ms.assetid: 43f27e56-a6aa-4548-9c96-000e53a7eb9a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetOutputCallbacks method [Windows Debugging], IDebugClient interface, IDebugClient5 interface [Windows Debugging], GetOutputCallbacks method, IDebugClient2 interface [Windows Debugging], GetOutputCallbacks method, IDebugClient3::GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], IDebugClient3 interface, dbgeng/IDebugClient3::GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], IDebugClient2 interface, IDebugClient4 interface [Windows Debugging], GetOutputCallbacks method, IDebugClient_693aaf2a-8408-48c4-b7c0-66e7064a6f35.xml, dbgeng/IDebugClient::GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], IDebugClient4::GetOutputCallbacks, IDebugClient5::GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], IDebugClient5 interface, IDebugClient2, GetOutputCallbacks, dbgeng/IDebugClient4::GetOutputCallbacks, IDebugClient2::GetOutputCallbacks, debugger.getoutputcallbacks, dbgeng/IDebugClient2::GetOutputCallbacks, IDebugClient interface [Windows Debugging], GetOutputCallbacks method, IDebugClient3, IDebugClient::GetOutputCallbacks, IDebugClient3 interface [Windows Debugging], GetOutputCallbacks method, IDebugClient, dbgeng/IDebugClient5::GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], IDebugClient4 interface
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
-	IDebugClient.GetOutputCallbacks
-	IDebugClient2.GetOutputCallbacks
-	IDebugClient3.GetOutputCallbacks
-	IDebugClient4.GetOutputCallbacks
-	IDebugClient5.GetOutputCallbacks
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient3::GetOutputCallbacks method


## -description


The <b>GetOutputCallbacks</b> method returns the <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> object registered with the client.


## -syntax


````
HRESULT GetOutputCallbacks(
  [out] PDEBUG_OUTPUT_CALLBACKS *Callbacks
);
````


## -parameters




### -param Callbacks [out]

Receives an interface pointer to the <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a> object registered with the client.


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



Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

If no output callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugOutputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugOutputCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetOutputCallbacks method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

