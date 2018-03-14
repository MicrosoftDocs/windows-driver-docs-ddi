---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemId
title: IDebugSystemObjects3::GetCurrentSystemId method
author: windows-driver-content
description: The GetCurrentSystemId method returns the engine target ID for the current process.
old-location: debugger\getcurrentsystemid.htm
old-project: debugger
ms.assetid: 2ff5091b-7cf8-4972-b87b-b18d25bb23e9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCurrentSystemId method [Windows Debugging], GetCurrentSystemId method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentSystemId method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentSystemId,IDebugSystemObjects3.GetCurrentSystemId, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentSystemId method, IDebugSystemObjects3::GetCurrentSystemId, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentSystemId method, IDebugSystemObjects4::GetCurrentSystemId, IDebugSystemObjects_02c8ff30-b552-465a-9be3-4e0526e1d6e1.xml, dbgeng/IDebugSystemObjects3::GetCurrentSystemId, dbgeng/IDebugSystemObjects4::GetCurrentSystemId, debugger.getcurrentsystemid
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
-	IDebugSystemObjects3.GetCurrentSystemId
-	IDebugSystemObjects4.GetCurrentSystemId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects3::GetCurrentSystemId method


## -description


The <b>GetCurrentSystemId</b> method returns the engine target ID for the current process.


## -syntax


````
HRESULT GetCurrentSystemId(
  [out] PULONG Id
);
````


## -parameters




### -param Id [out]

Receives the engine target ID.


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
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>



 

 


