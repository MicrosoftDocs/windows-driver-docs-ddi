---
UID: NF:dbgeng.IDebugClient5.GetNumberOutputCallbacks
title: IDebugClient5::GetNumberOutputCallbacks (dbgeng.h)
description: The GetNumberOutputCallbacks method returns the number of output callbacks registered over all clients.
old-location: debugger\getnumberoutputcallbacks.htm
tech.root: debugger
ms.assetid: 20bc6141-8c4a-4a98-acb3-506840893db6
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetNumberOutputCallbacks"]
ms.keywords: GetNumberOutputCallbacks, GetNumberOutputCallbacks method [Windows Debugging], GetNumberOutputCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetNumberOutputCallbacks method, IDebugClient5.GetNumberOutputCallbacks, IDebugClient5::GetNumberOutputCallbacks, IDebugClient_ce6e107b-a356-434a-81d7-eccb8495289d.xml, dbgeng/IDebugClient5::GetNumberOutputCallbacks, debugger.getnumberoutputcallbacks
f1_keywords:
 - "dbgeng/IDebugClient5.GetNumberOutputCallbacks"
 - "IDebugClient5.GetNumberOutputCallbacks"
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
- IDebugClient5.GetNumberOutputCallbacks
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetNumberOutputCallbacks


## -description


The <b>GetNumberOutputCallbacks</b> method returns the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a> registered over all clients.


## -parameters




### -param Count 
[out]
Receives the number of output callbacks that have been registered.


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



Each client can have at most one output callback registered with it.

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumbereventcallbacks">GetNumberEventCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumberinputcallbacks">GetNumberInputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getoutputcallbacks">GetOutputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a>
 

 

