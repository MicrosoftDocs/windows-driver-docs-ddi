---
UID: NF:dbgeng.IDebugEventCallbacks.CreateThread
title: IDebugEventCallbacks::CreateThread method
author: windows-driver-content
description: The CreateThread callback method is called by the engine when a create-threaddebugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_createthread.htm
old-project: debugger
ms.assetid: c3b2cbaa-33b9-4784-922d-d1209fc23dfd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugEventCallbacks, IDebugEventCallbacks::CreateThread, CreateThread
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
req.alt-api: IDebugEventCallbacks.CreateThread
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

# IDebugEventCallbacks::CreateThread method



## -description
The <b>CreateThread</b> callback method is called by the engine when a create-threaddebugging event occurs in the target.



## -syntax

````
HRESULT CreateThread(
  [in] ULONG64 Handle,
  [in] ULONG64 DataOffset,
  [in] ULONG64 StartOffset
);
````


## -parameters

### -param Handle [in]

Specifies the handle for the thread whose creation caused the event.  If this information is not available, <i>Handle</i> will be <b>NULL</b>.


### -param DataOffset [in]

Specifies a block of data that the operating system maintains for this thread. The actual data in the block is operating system-specific.  If the operating system does not have such a block, <i>DataOffset</i> will be <b>NULL</b>.


### -param StartOffset [in]

Specifies the starting location in the target's virtual address space of the thread.  If this information is not available, <i>StartOffset</i> will be <b>NULL</b>.


## -returns
This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.


## -remarks
This method is only called by the engine if the DEBUG_EVENT_CREATE_THREAD flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>