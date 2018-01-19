---
UID: NF:dbgeng.IDebugSystemObjects4.SetCurrentThreadId
title: IDebugSystemObjects4::SetCurrentThreadId method
author: windows-driver-content
description: The SetCurrentThreadId method makes the specified thread the current thread.
old-location: debugger\setcurrentthreadid.htm
old-project: debugger
ms.assetid: 965c2fe0-5be5-4036-b649-a25fcc6e2dc2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetCurrentThreadId, SetCurrentThreadId
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
req.alt-api: IDebugSystemObjects.SetCurrentThreadId,IDebugSystemObjects2.SetCurrentThreadId,IDebugSystemObjects3.SetCurrentThreadId,IDebugSystemObjects4.SetCurrentThreadId
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

# IDebugSystemObjects4::SetCurrentThreadId method



## -description
The <b>SetCurrentThreadId</b> method makes the specified thread the current thread.



## -syntax

````
HRESULT SetCurrentThreadId(
  [in] ULONG Id
);
````


## -parameters

### -param Id [in]

Specifies the engine thread ID of the thread that is to become the current thread.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>No thread with the specified ID was found.

 


## -remarks
This method may also change the current process, current target, and current computer.

If the thread is changed, the callback <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on monitoring events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>