---
UID: NF:dbgeng.IDebugClient3.SetOutputCallbacks
title: IDebugClient3::SetOutputCallbacks method
author: windows-driver-content
description: The SetOutputCallbacks method registers an output callbacks object with this client.
old-location: debugger\setoutputcallbacks.htm
old-project: debugger
ms.assetid: 2226804c-dbdd-4855-9ba5-7c1959941e59
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetOutputCallbacks method, IDebugClient2 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient2::SetOutputCallbacks, IDebugClient3, IDebugClient3 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient3::SetOutputCallbacks, IDebugClient4 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient4::SetOutputCallbacks, IDebugClient5 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient5::SetOutputCallbacks, IDebugClient::SetOutputCallbacks, IDebugClient_b1da4bc1-b368-475e-bd13-021358f9d234.xml, SetOutputCallbacks method [Windows Debugging], SetOutputCallbacks method [Windows Debugging], IDebugClient interface, SetOutputCallbacks method [Windows Debugging], IDebugClient2 interface, SetOutputCallbacks method [Windows Debugging], IDebugClient3 interface, SetOutputCallbacks method [Windows Debugging], IDebugClient4 interface, SetOutputCallbacks method [Windows Debugging], IDebugClient5 interface, SetOutputCallbacks,IDebugClient3.SetOutputCallbacks, dbgeng/IDebugClient2::SetOutputCallbacks, dbgeng/IDebugClient3::SetOutputCallbacks, dbgeng/IDebugClient4::SetOutputCallbacks, dbgeng/IDebugClient5::SetOutputCallbacks, dbgeng/IDebugClient::SetOutputCallbacks, debugger.setoutputcallbacks
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.SetOutputCallbacks
-	IDebugClient2.SetOutputCallbacks
-	IDebugClient3.SetOutputCallbacks
-	IDebugClient4.SetOutputCallbacks
-	IDebugClient5.SetOutputCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient3::SetOutputCallbacks method


## -description


The <b>SetOutputCallbacks</b> method registers an <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> object with this client.


## -syntax


````
HRESULT SetOutputCallbacks(
  [in, optional] PDEBUG_OUTPUT_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [in, optional]

Specifies the interface pointer to the output callbacks object to register with this client.


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



Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacks</b> object registered with it for output.

The <b>IDebugOutputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetOutputCallbacks</b> and <b>SetOutputCAllbacksWide</b> call the <b>IUnknown::AddRef</b> method in the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetOutputCallbacks</b> or <b>SetOutputCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548071">GetOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetOutputCallbacks method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

