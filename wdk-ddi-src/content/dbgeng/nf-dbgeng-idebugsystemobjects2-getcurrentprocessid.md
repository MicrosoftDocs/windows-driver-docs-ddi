---
UID: NF:dbgeng.IDebugSystemObjects2.GetCurrentProcessId
title: IDebugSystemObjects2::GetCurrentProcessId method
author: windows-driver-content
description: The GetCurrentProcessId method returns the engine process ID for the current process.
old-location: debugger\getcurrentprocessid.htm
old-project: debugger
ms.assetid: 5b256ccb-8f03-4936-8e03-9955c81384a5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, C, D, G, GetCurrentProcessId method [Windows Debugging], GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects interface, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentProcessId,IDebugSystemObjects.GetCurrentProcessId, GetCurrentProcessId,IDebugSystemObjects2.GetCurrentProcessId, I, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects2::GetCurrentProcessId, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects3::GetCurrentProcessId, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects4::GetCurrentProcessId, IDebugSystemObjects::GetCurrentProcessId, IDebugSystemObjects_9ae912e7-68db-45d0-8129-f55e5b3ee462.xml, O, P, S, b, c, d, dbgeng/IDebugSystemObjects2::GetCurrentProcessId, dbgeng/IDebugSystemObjects3::GetCurrentProcessId, dbgeng/IDebugSystemObjects4::GetCurrentProcessId, dbgeng/IDebugSystemObjects::GetCurrentProcessId, debugger.getcurrentprocessid, e, g, j, m, n, o, r, s, t, u, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects.GetCurrentProcessId
-	IDebugSystemObjects2.GetCurrentProcessId
-	IDebugSystemObjects3.GetCurrentProcessId
-	IDebugSystemObjects4.GetCurrentProcessId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects2::GetCurrentProcessId method


## -description


The <b>GetCurrentProcessId</b> method returns the engine process ID for the current process.


## -syntax


````
HRESULT GetCurrentProcessId(
  [out] PULONG Id
);
````


## -parameters




### -param Id [out]

Receives the engine process ID for the current process.


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



For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



