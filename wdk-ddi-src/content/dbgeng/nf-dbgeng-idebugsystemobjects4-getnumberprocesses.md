---
UID: NF:dbgeng.IDebugSystemObjects4.GetNumberProcesses
title: IDebugSystemObjects4::GetNumberProcesses method
author: windows-driver-content
description: The GetNumberProcesses method returns the number of processes for the current target.
old-location: debugger\getnumberprocesses.htm
old-project: debugger
ms.assetid: bf0c750f-0e29-42d9-a127-953e3d49b969
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetNumberProcesses, GetNumberProcesses
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
req.alt-api: IDebugSystemObjects.GetNumberProcesses,IDebugSystemObjects2.GetNumberProcesses,IDebugSystemObjects3.GetNumberProcesses,IDebugSystemObjects4.GetNumberProcesses
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

# IDebugSystemObjects4::GetNumberProcesses method



## -description
The <b>GetNumberProcesses</b> method returns the number of <a href="debugger.controlling_threads_and_processes#processes#processes">processes</a> for the current target.



## -syntax

````
HRESULT GetNumberProcesses(
  [out] PULONG Number
);
````


## -parameters

### -param Number [out]

Receives the number of processes.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, there is only a single virtual process representing the kernel.

In user-mode debugging, the number of processes changes with the create-process and exit-process debugging <a href="debugger.events#events#events">events</a>.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>