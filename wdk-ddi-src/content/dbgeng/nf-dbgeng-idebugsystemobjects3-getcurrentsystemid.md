---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemId
title: IDebugSystemObjects3::GetCurrentSystemId
author: windows-driver-content
description: The GetCurrentSystemId method returns the engine target ID for the current process.
old-location: debugger\getcurrentsystemid.htm
old-project: debugger
ms.assetid: 2ff5091b-7cf8-4972-b87b-b18d25bb23e9
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetCurrentSystemId, GetCurrentSystemId method [Windows Debugging], GetCurrentSystemId method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentSystemId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentSystemId method, IDebugSystemObjects3.GetCurrentSystemId, IDebugSystemObjects3::GetCurrentSystemId, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentSystemId method, IDebugSystemObjects4::GetCurrentSystemId, IDebugSystemObjects_02c8ff30-b552-465a-9be3-4e0526e1d6e1.xml, dbgeng/IDebugSystemObjects3::GetCurrentSystemId, dbgeng/IDebugSystemObjects4::GetCurrentSystemId, debugger.getcurrentsystemid
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetCurrentSystemId


## -description


The <b>GetCurrentSystemId</b> method returns the engine target ID for the current process.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550892">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550893">IDebugSystemObjects4</a>
 

 

