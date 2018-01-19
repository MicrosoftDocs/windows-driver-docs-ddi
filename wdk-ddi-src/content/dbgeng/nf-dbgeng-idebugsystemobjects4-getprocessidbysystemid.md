---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdBySystemId
title: IDebugSystemObjects4::GetProcessIdBySystemId method
author: windows-driver-content
description: The GetProcessIdBySystemId method returns the engine process ID for a process specified by its system process ID.
old-location: debugger\getprocessidbysystemid.htm
old-project: debugger
ms.assetid: 7260f0ea-5e8b-4b08-8c8f-70216ffe54a9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetProcessIdBySystemId, GetProcessIdBySystemId
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
req.alt-api: IDebugSystemObjects.GetProcessIdBySystemId,IDebugSystemObjects2.GetProcessIdBySystemId,IDebugSystemObjects3.GetProcessIdBySystemId,IDebugSystemObjects4.GetProcessIdBySystemId
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSystemObjects4::GetProcessIdBySystemId method



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The target is a kernel-mode target.

 


## -remarks
This method is only available in user-mode debugging.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>