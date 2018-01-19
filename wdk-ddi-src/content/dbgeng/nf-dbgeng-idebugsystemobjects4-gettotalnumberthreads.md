---
UID: NF:dbgeng.IDebugSystemObjects4.GetTotalNumberThreads
title: IDebugSystemObjects4::GetTotalNumberThreads method
author: windows-driver-content
description: The GetTotalNumberThreads method returns the total number of threads for all the processes in the current target, in addition to the largest number of threads in any process for the current target.
old-location: debugger\gettotalnumberthreads.htm
old-project: debugger
ms.assetid: dce67b78-a5e0-4664-b183-f462bcd773c8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetTotalNumberThreads, GetTotalNumberThreads
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
req.alt-api: IDebugSystemObjects.GetTotalNumberThreads,IDebugSystemObjects2.GetTotalNumberThreads,IDebugSystemObjects3.GetTotalNumberThreads,IDebugSystemObjects4.GetTotalNumberThreads
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

# IDebugSystemObjects4::GetTotalNumberThreads method



## -description
The <b>GetTotalNumberThreads</b> method returns the total number of <a href="debugger.controlling_threads_and_processes#threads#threads">threads</a> for all the <a href="debugger.controlling_threads_and_processes#processes#processes">processes</a> in the current target, in addition to the largest number of threads in any process for the current target.



## -syntax

````
HRESULT GetTotalNumberThreads(
  [out] PULONG Total,
  [out] PULONG LargestProcess
);
````


## -parameters

### -param Total [out]

Receives the total number of threads for all the processes in the current target.


### -param LargestProcess [out]

Receives the largest number of threads in any process for the current target.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>