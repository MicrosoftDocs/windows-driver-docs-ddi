---
UID: NF:dbgeng.IDebugSystemObjects3.GetSystemByServer
title: IDebugSystemObjects3::GetSystemByServer
author: windows-driver-content
description: Gets the system for a server.
old-location: debugger\idebugsystemobjects3_getsystembyserver.htm
tech.root: debugger
ms.assetid: 693CB919-A1D1-4A82-ABE5-2362431A9B92
ms.date: 5/3/2018
ms.keywords: GetSystemByServer, GetSystemByServer method [Windows Debugging], GetSystemByServer method [Windows Debugging],IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging],GetSystemByServer method, IDebugSystemObjects3.GetSystemByServer, IDebugSystemObjects3::GetSystemByServer, dbgeng/IDebugSystemObjects3::GetSystemByServer, debugger.idebugsystemobjects3_getsystembyserver
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
-	IDebugSystemObjects3.GetSystemByServer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetSystemByServer


## -description


Gets the system for a server.


## -parameters




### -param Server




### -param Id






#### - Buffer [out]

A pointer to an output buffer. 


#### - BufferSize [in]

The size of the buffer.


#### - NameSize [out, optional]

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
 

 

