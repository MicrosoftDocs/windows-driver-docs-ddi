---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemServerName
title: IDebugSystemObjects3::GetCurrentSystemServerName
author: windows-driver-content
description: Gets the server name for the current process.
old-location: debugger\idebugsystemobjects3_getcurrentsystemservername.htm
tech.root: debugger
ms.assetid: 4E06AFD0-42D3-479F-B285-34919826F750
ms.date: 05/03/2018
ms.keywords: GetCurrentSystemServerName, GetCurrentSystemServerName method [Windows Debugging], GetCurrentSystemServerName method [Windows Debugging],IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentSystemServerName method, IDebugSystemObjects3.GetCurrentSystemServerName, IDebugSystemObjects3::GetCurrentSystemServerName, dbgeng/IDebugSystemObjects3::GetCurrentSystemServerName, debugger.idebugsystemobjects3_getcurrentsystemservername
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	Dbgeng.h
api_name:
-	IDebugSystemObjects3.GetCurrentSystemServerName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetCurrentSystemServerName


## -description


Gets the server name for the current process.


## -parameters




### -param Buffer [out]

A pointer to an output buffer.


### -param BufferSize [in]

The size of the buffer.


### -param NameSize [out, optional]

A pointer to the name size. 


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
 

 

