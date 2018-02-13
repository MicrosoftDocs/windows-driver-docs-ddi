---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdByHandle
title: IDebugSystemObjects4::GetProcessIdByHandle method
author: windows-driver-content
description: The GetProcessIdByHandle method returns the engine process ID for the specified process. The process is specified by its system handle.
old-location: debugger\getprocessidbyhandle.htm
old-project: debugger
ms.assetid: 6920cbd3-0a20-4d38-8538-85f46d0f0d5b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects interface [Windows Debugging], GetProcessIdByHandle method, IDebugSystemObjects2::GetProcessIdByHandle, GetProcessIdByHandle method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects::GetProcessIdByHandle, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdByHandle method, IDebugSystemObjects::GetProcessIdByHandle, IDebugSystemObjects3::GetProcessIdByHandle, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdByHandle method, IDebugSystemObjects4::GetProcessIdByHandle, debugger.getprocessidbyhandle, GetProcessIdByHandle method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects3::GetProcessIdByHandle, GetProcessIdByHandle method [Windows Debugging], dbgeng/IDebugSystemObjects2::GetProcessIdByHandle, GetProcessIdByHandle method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects_92e69c0f-a50c-498b-8352-74f0c28ea0d8.xml, IDebugSystemObjects4, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdByHandle method, GetProcessIdByHandle, dbgeng/IDebugSystemObjects4::GetProcessIdByHandle, IDebugSystemObjects3, GetProcessIdByHandle method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects
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
-	IDebugSystemObjects.GetProcessIdByHandle
-	IDebugSystemObjects2.GetProcessIdByHandle
-	IDebugSystemObjects3.GetProcessIdByHandle
-	IDebugSystemObjects4.GetProcessIdByHandle
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects4::GetProcessIdByHandle method


## -description


The <b>GetProcessIdByHandle</b> method returns the engine process ID for the specified process.  The process is specified by its system handle.


## -syntax


````
HRESULT GetProcessIdByHandle(
  [in]  ULONG64 Handle,
  [out] PULONG  Id
);
````


## -parameters




### -param Handle [in]

Specifies the handle of the process whose process ID is requested.  This handle must be a process handle previously retrieved from the debugger engine.


### -param Id [out]

Receives the engine process ID.


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



For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on system handles, see <a href="https://msdn.microsoft.com/3be5c842-d1b6-4c34-8990-e23e2d08dd23">Handles</a>.



