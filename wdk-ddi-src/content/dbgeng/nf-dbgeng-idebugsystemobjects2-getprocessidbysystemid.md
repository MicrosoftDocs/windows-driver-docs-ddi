---
UID: NF:dbgeng.IDebugSystemObjects2.GetProcessIdBySystemId
title: IDebugSystemObjects2::GetProcessIdBySystemId method
author: windows-driver-content
description: The GetProcessIdBySystemId method returns the engine process ID for a process specified by its system process ID.
old-location: debugger\getprocessidbysystemid.htm
old-project: debugger
ms.assetid: 7260f0ea-5e8b-4b08-8c8f-70216ffe54a9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects3::GetProcessIdBySystemId, debugger.getprocessidbysystemid, dbgeng/IDebugSystemObjects2::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects4::GetProcessIdBySystemId, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects4 interface, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects3 interface, GetProcessIdBySystemId, IDebugSystemObjects interface [Windows Debugging], GetProcessIdBySystemId method, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdBySystemId method, dbgeng/IDebugSystemObjects::GetProcessIdBySystemId, IDebugSystemObjects2::GetProcessIdBySystemId, IDebugSystemObjects::GetProcessIdBySystemId, IDebugSystemObjects4::GetProcessIdBySystemId, IDebugSystemObjects_45c888bc-6771-4cd4-843e-aeafd8c6c6cb.xml, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects2 interface, dbgeng/IDebugSystemObjects3::GetProcessIdBySystemId, IDebugSystemObjects2, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdBySystemId method, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdBySystemId method, IDebugSystemObjects
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
-	IDebugSystemObjects.GetProcessIdBySystemId
-	IDebugSystemObjects2.GetProcessIdBySystemId
-	IDebugSystemObjects3.GetProcessIdBySystemId
-	IDebugSystemObjects4.GetProcessIdBySystemId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects2::GetProcessIdBySystemId method


## -description


The <b>GetProcessIdBySystemId</b> method returns the engine process ID for a process specified by its system process ID.


## -syntax


````
HRESULT GetProcessIdBySystemId(
  [in]  ULONG  SysId,
  [out] PULONG Id
);
````


## -parameters




### -param SysId [in]

Specifies the system process ID.


### -param Id [out]

Receives the engine process ID.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.

</td>
</tr>
</table>
 




## -remarks



This method is only available in user-mode debugging.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



