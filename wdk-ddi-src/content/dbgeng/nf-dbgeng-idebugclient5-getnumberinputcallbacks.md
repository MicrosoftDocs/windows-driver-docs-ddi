---
UID: NF:dbgeng.IDebugClient5.GetNumberInputCallbacks
title: IDebugClient5::GetNumberInputCallbacks method
author: windows-driver-content
description: The GetNumberInputCallbacks method returns the number of input callbacks registered over all clients.
old-location: debugger\getnumberinputcallbacks.htm
old-project: debugger
ms.assetid: 25188616-ac1a-4699-9343-0fa88e27d9b8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNumberInputCallbacks method [Windows Debugging], GetNumberInputCallbacks method [Windows Debugging], IDebugClient5 interface, GetNumberInputCallbacks,IDebugClient5.GetNumberInputCallbacks, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetNumberInputCallbacks method, IDebugClient5::GetNumberInputCallbacks, IDebugClient_ccf5fe3e-20d9-4415-bcfd-4823960acd05.xml, dbgeng/IDebugClient5::GetNumberInputCallbacks, debugger.getnumberinputcallbacks
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
-	IDebugClient5.GetNumberInputCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetNumberInputCallbacks method


## -description


The <b>GetNumberInputCallbacks</b> method returns the number of <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">input callbacks</a> registered over all clients.


## -syntax


````
HRESULT GetNumberInputCallbacks(
  [out] PULONG Count
);
````


## -parameters




### -param Count [out]

Receives the number of input callbacks that have been registered.


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



Each client can have at most one input callback registered with it.

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546892">GetInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547896">GetNumberEventCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547931">GetNumberOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556721">SetInputCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetNumberInputCallbacks method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

