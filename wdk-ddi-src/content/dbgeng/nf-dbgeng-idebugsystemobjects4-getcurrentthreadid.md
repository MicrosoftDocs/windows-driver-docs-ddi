---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadId
title: IDebugSystemObjects4::GetCurrentThreadId method
author: windows-driver-content
description: The GetCurrentThreadId method returns the engine thread ID for the current thread.
old-location: debugger\getcurrentthreadid.htm
old-project: debugger
ms.assetid: 7062c962-2e82-40e3-81ea-97ac0948e501
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentThreadId, GetCurrentThreadId
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
req.alt-api: IDebugSystemObjects.GetCurrentThreadId,IDebugSystemObjects2.GetCurrentThreadId,IDebugSystemObjects3.GetCurrentThreadId,IDebugSystemObjects4.GetCurrentThreadId
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

# IDebugSystemObjects4::GetCurrentThreadId method



## -description
The <b>GetCurrentThreadId</b> method returns the engine thread ID for the current thread.



## -syntax

````
HRESULT GetCurrentThreadId(
  [out] PULONG Id
);
````


## -parameters

### -param Id [out]

Receives the engine thread ID.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>