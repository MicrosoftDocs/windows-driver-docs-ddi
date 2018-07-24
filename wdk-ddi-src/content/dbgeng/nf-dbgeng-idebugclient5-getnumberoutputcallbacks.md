---
UID: NF:dbgeng.IDebugClient5.GetNumberOutputCallbacks
title: IDebugClient5::GetNumberOutputCallbacks
author: windows-driver-content
description: The GetNumberOutputCallbacks method returns the number of output callbacks registered over all clients.
old-location: debugger\getnumberoutputcallbacks.htm
tech.root: debugger
ms.assetid: 20bc6141-8c4a-4a98-acb3-506840893db6
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetNumberOutputCallbacks, GetNumberOutputCallbacks method [Windows Debugging], GetNumberOutputCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetNumberOutputCallbacks method, IDebugClient5.GetNumberOutputCallbacks, IDebugClient5::GetNumberOutputCallbacks, IDebugClient_ce6e107b-a356-434a-81d7-eccb8495289d.xml, dbgeng/IDebugClient5::GetNumberOutputCallbacks, debugger.getnumberoutputcallbacks
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
-	IDebugClient5.GetNumberOutputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetNumberOutputCallbacks


## -description


The <b>GetNumberOutputCallbacks</b> method returns the number of <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> registered over all clients.


## -parameters




### -param Count [out]

Receives the number of output callbacks that have been registered.


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



Each client can have at most one output callback registered with it.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547896">GetNumberEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547923">GetNumberInputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548071">GetOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>
 

 

