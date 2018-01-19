---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessId
title: IDebugSystemObjects4::GetCurrentProcessId method
author: windows-driver-content
description: The GetCurrentProcessId method returns the engine process ID for the current process.
old-location: debugger\getcurrentprocessid.htm
old-project: debugger
ms.assetid: 5b256ccb-8f03-4936-8e03-9955c81384a5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentProcessId, GetCurrentProcessId
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
req.alt-api: IDebugSystemObjects.GetCurrentProcessId,IDebugSystemObjects2.GetCurrentProcessId,IDebugSystemObjects3.GetCurrentProcessId,IDebugSystemObjects4.GetCurrentProcessId
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

# IDebugSystemObjects4::GetCurrentProcessId method



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>