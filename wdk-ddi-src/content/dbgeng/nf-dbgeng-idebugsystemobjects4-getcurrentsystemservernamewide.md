---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentSystemServerNameWide
title: IDebugSystemObjects4::GetCurrentSystemServerNameWide method
author: windows-driver-content
description: Gets the server name for the current process.
old-location: debugger\idebugsystemobjects4_getcurrentsystemservernamewide.htm
old-project: debugger
ms.assetid: 44BAB9BF-76E6-42C2-B8DD-EB1A960C429C
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetCurrentSystemServerNameWide method [Windows Debugging], GetCurrentSystemServerNameWide method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentSystemServerNameWide,IDebugSystemObjects4.GetCurrentSystemServerNameWide, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentSystemServerNameWide method, IDebugSystemObjects4::GetCurrentSystemServerNameWide, dbgeng/IDebugSystemObjects4::GetCurrentSystemServerNameWide, debugger.idebugsystemobjects4_getcurrentsystemservernamewide
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: dbgeng.h
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
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects4::GetCurrentSystemServerNameWide method


## -description


Gets the server name for the current process.


## -syntax


````
HRESULT GetCurrentSystemServerNameWide(
  [out]           _writes_opt_(BufferSize) PWSTR Buffer,
  [in]            ULONG                          BufferSize,
  [out, optional] PULONG                         NameSize
);
````


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



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects4::GetCurrentSystemServerNameWide method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

