---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdByHandle
title: IDebugSystemObjects4::GetProcessIdByHandle method
author: windows-driver-content
description: The GetProcessIdByHandle method returns the engine process ID for the specified process. The process is specified by its system handle.
old-location: debugger\getprocessidbyhandle.htm
old-project: debugger
ms.assetid: 6920cbd3-0a20-4d38-8538-85f46d0f0d5b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetProcessIdByHandle, GetProcessIdByHandle
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
req.alt-api: IDebugSystemObjects.GetProcessIdByHandle,IDebugSystemObjects2.GetProcessIdByHandle,IDebugSystemObjects3.GetProcessIdByHandle,IDebugSystemObjects4.GetProcessIdByHandle
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on system handles, see <a href="wdkgloss.h#wdkgloss.handle#wdkgloss.handle"><i>Handles</i></a>.</p>