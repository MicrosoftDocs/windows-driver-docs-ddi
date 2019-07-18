---
UID: NF:dbgeng.IDebugClient4.SetInputCallbacks
title: IDebugClient4::SetInputCallbacks (dbgeng.h)
description: The SetInputCallbacks method registers an input callbacks object with the client.
old-location: debugger\setinputcallbacks.htm
tech.root: debugger
ms.assetid: 4fd7ba5f-c400-4f44-bebb-b52e9a579f99
ms.date: 05/03/2018
ms.keywords: IDebugClient interface [Windows Debugging],SetInputCallbacks method, IDebugClient2 interface [Windows Debugging],SetInputCallbacks method, IDebugClient2::SetInputCallbacks, IDebugClient3 interface [Windows Debugging],SetInputCallbacks method, IDebugClient3::SetInputCallbacks, IDebugClient4 interface [Windows Debugging],SetInputCallbacks method, IDebugClient4.SetInputCallbacks, IDebugClient4::SetInputCallbacks, IDebugClient5 interface [Windows Debugging],SetInputCallbacks method, IDebugClient5::SetInputCallbacks, IDebugClient::SetInputCallbacks, IDebugClient_fea0d021-69b2-462f-965f-455305fd5971.xml, SetInputCallbacks, SetInputCallbacks method [Windows Debugging], SetInputCallbacks method [Windows Debugging],IDebugClient interface, SetInputCallbacks method [Windows Debugging],IDebugClient2 interface, SetInputCallbacks method [Windows Debugging],IDebugClient3 interface, SetInputCallbacks method [Windows Debugging],IDebugClient4 interface, SetInputCallbacks method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetInputCallbacks, dbgeng/IDebugClient3::SetInputCallbacks, dbgeng/IDebugClient4::SetInputCallbacks, dbgeng/IDebugClient5::SetInputCallbacks, dbgeng/IDebugClient::SetInputCallbacks, debugger.setinputcallbacks
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugClient.SetInputCallbacks"
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
- IDebugClient.SetInputCallbacks
- IDebugClient2.SetInputCallbacks
- IDebugClient3.SetInputCallbacks
- IDebugClient4.SetInputCallbacks
- IDebugClient5.SetInputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient4::SetInputCallbacks


## -description


The <b>SetInputCallbacks</b> method registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">input callbacks</a> object with the client.


## -parameters




### -param Callbacks [in, optional]

Specifies the interface pointer to the input callbacks object to register with this client.


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



Each client can have at most one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a> object registered with it to receive requests for input.

The <b>IDebugInputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetInputCallbacks</b> will call the <b>IUnknown::AddRef</b> method of the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetInputCallbacks</b> is called on this client, or when this client is deleted.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-getinputcallbacks">GetInputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a>
 

 

