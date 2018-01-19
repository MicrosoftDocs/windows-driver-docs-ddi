---
UID: NF:dbgeng.IDebugSystemObjects4.GetNumberThreads
title: IDebugSystemObjects4::GetNumberThreads method
author: windows-driver-content
description: The GetNumberThreads method returns the number of threads in the current process.
old-location: debugger\getnumberthreads.htm
old-project: debugger
ms.assetid: f56da2d0-4c4c-4302-a87b-c672dec25d9f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetNumberThreads, GetNumberThreads
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
req.alt-api: IDebugSystemObjects.GetNumberThreads,IDebugSystemObjects2.GetNumberThreads,IDebugSystemObjects3.GetNumberThreads,IDebugSystemObjects4.GetNumberThreads
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

# IDebugSystemObjects4::GetNumberThreads method



## -description
The <b>GetNumberThreads</b> method returns the number of <a href="debugger.controlling_threads_and_processes#threads#threads">threads</a> in the current process.



## -syntax

````
HRESULT GetNumberThreads(
  [out] PULONG Number
);
````


## -parameters

### -param Number [out]

Receives the number of threads in the current process.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, there is a virtual thread representing each processor.

In user-mode debugging, the number of threads changes with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550713">IDebugEventCallbacks::CreateThread</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550730">IDebugEventCallbacks::ExitThread</a> events.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>