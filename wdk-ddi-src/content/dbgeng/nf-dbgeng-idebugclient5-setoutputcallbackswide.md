---
UID: NF:dbgeng.IDebugClient5.SetOutputCallbacksWide
title: IDebugClient5::SetOutputCallbacksWide
author: windows-driver-content
description: The SetOutputCallbacksWide method registers an output callbacks object with this client.
old-location: debugger\setoutputcallbackswide.htm
old-project: debugger
ms.assetid: cd6f68b2-2a62-4607-8c70-11a94fd75ecb
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],SetOutputCallbacksWide method, IDebugClient5.SetOutputCallbacksWide, IDebugClient5::SetOutputCallbacksWide, SetOutputCallbacksWide, SetOutputCallbacksWide method [Windows Debugging], SetOutputCallbacksWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::SetOutputCallbacksWide, debugger.setoutputcallbackswide
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
-	IDebugClient5.SetOutputCallbacksWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::SetOutputCallbacksWide


## -description


The <b>SetOutputCallbacksWide</b> method registers an <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> object with this client.


## -parameters




### -param Callbacks [in]

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



Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

The <b>IDebugOutputCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetOutputCallbacks</b> and <b>SetOutputCAllbacksWide</b> call the <b>IUnknown::AddRef</b> method in the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetOutputCallbacks</b> or <b>SetOutputCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548071">GetOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a>
 

 

