---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentSystemServerNameWide
title: IDebugSystemObjects4::GetCurrentSystemServerNameWide
description: Gets the server name for the current process.
old-location: debugger\idebugsystemobjects4_getcurrentsystemservernamewide.htm
tech.root: debugger
ms.assetid: 44BAB9BF-76E6-42C2-B8DD-EB1A960C429C
ms.date: 05/03/2018
ms.keywords: GetCurrentSystemServerNameWide, GetCurrentSystemServerNameWide method [Windows Debugging], GetCurrentSystemServerNameWide method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentSystemServerNameWide method, IDebugSystemObjects4.GetCurrentSystemServerNameWide, IDebugSystemObjects4::GetCurrentSystemServerNameWide, dbgeng/IDebugSystemObjects4::GetCurrentSystemServerNameWide, debugger.idebugsystemobjects4_getcurrentsystemservernamewide
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
-	IDebugSystemObjects4.GetCurrentSystemServerNameWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects4::GetCurrentSystemServerNameWide


## -description


Gets the server name for the current process.


## -parameters




### -param Buffer [out]

A pointer to an output buffer as a Unicode character string. 


### -param BufferSize [in]

The buffer size. 


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550893">IDebugSystemObjects4</a>
 

 

