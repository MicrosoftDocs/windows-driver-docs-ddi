---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadSystemId
title: IDebugSystemObjects4::GetCurrentThreadSystemId method
author: windows-driver-content
description: The GetCurrentThreadSystemId method returns the system thread ID of the current thread.
old-location: debugger\getcurrentthreadsystemid.htm
old-project: debugger
ms.assetid: b2e4d14c-a97f-4f57-b0ce-5a52a82c1690
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentThreadSystemId, GetCurrentThreadSystemId
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
req.alt-api: IDebugSystemObjects.GetCurrentThreadSystemId,IDebugSystemObjects2.GetCurrentThreadSystemId,IDebugSystemObjects3.GetCurrentThreadSystemId,IDebugSystemObjects4.GetCurrentThreadSystemId
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

# IDebugSystemObjects4::GetCurrentThreadSystemId method



## -description
The <b>GetCurrentThreadSystemId</b> method returns the system thread ID of the current thread.



## -syntax

````
HRESULT GetCurrentThreadSystemId(
  [out] PULONG SysId
);
````


## -parameters

### -param SysId [out]

Receives the system thread ID.


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

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>