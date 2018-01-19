---
UID: NF:dbgeng.IDebugSystemObjects4.SetCurrentProcessId
title: IDebugSystemObjects4::SetCurrentProcessId method
author: windows-driver-content
description: The SetCurrentProcessId method makes the specified process the current process.
old-location: debugger\setcurrentprocessid.htm
old-project: debugger
ms.assetid: 65129c6e-5c69-409b-95f5-07b98a494533
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetCurrentProcessId, SetCurrentProcessId
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
req.alt-api: IDebugSystemObjects.SetCurrentProcessId,IDebugSystemObjects2.SetCurrentProcessId,IDebugSystemObjects3.SetCurrentProcessId,IDebugSystemObjects4.SetCurrentProcessId
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

# IDebugSystemObjects4::SetCurrentProcessId method



## -description
The <b>SetCurrentProcessId</b> method makes the specified process the current process.



## -syntax

````
HRESULT SetCurrentProcessId(
  [in] ULONG Id
);
````


## -parameters

### -param Id [in]

Specifies the engine process ID for the process that is to become the current process.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>No process with the given process ID was found.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>No suitable candidate for the current thread could be found in the process.

 


## -remarks
This method also changes the current thread, and may change the current target and current computer.

If the process is changed, the callback <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on monitoring events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>