---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessHandle
title: IDebugSystemObjects4::GetCurrentProcessHandle method
author: windows-driver-content
description: The GetCurrentProcessHandle method returns the system handle for the current process.
old-location: debugger\getcurrentprocesshandle2.htm
old-project: debugger
ms.assetid: 87f60064-5722-4b4e-af9b-f1d9009a7551
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentProcessHandle, GetCurrentProcessHandle
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
req.alt-api: IDebugSystemObjects.GetCurrentProcessHandle,IDebugSystemObjects2.GetCurrentProcessHandle,IDebugSystemObjects3.GetCurrentProcessHandle,IDebugSystemObjects4.GetCurrentProcessHandle
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

# IDebugSystemObjects4::GetCurrentProcessHandle method



## -description
The <b>GetCurrentProcessHandle</b> method returns the system handle for the current process.



## -syntax

````
HRESULT GetCurrentProcessHandle(
  [out] PULONG64 Handle
);
````


## -parameters

### -param Handle [out]

Receives the system handle of the current process.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, the only process in the target is the virtual process created for the kernel.  In this case, an artificial handle is created.  The artificial handle can only be used with the debugger engine API.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on system handles, see <a href="wdkgloss.h#wdkgloss.handle#wdkgloss.handle"><i>Handles</i></a>.</p>