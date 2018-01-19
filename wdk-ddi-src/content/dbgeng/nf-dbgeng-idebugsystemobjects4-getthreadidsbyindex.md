---
UID: NF:dbgeng.IDebugSystemObjects4.GetThreadIdsByIndex
title: IDebugSystemObjects4::GetThreadIdsByIndex method
author: windows-driver-content
description: The GetThreadIdsByIndex method returns the engine and system thread IDs for the specified threads in the current process.
old-location: debugger\getthreadidsbyindex.htm
old-project: debugger
ms.assetid: d671ea6e-19cb-4a90-b345-ea544c9561cd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetThreadIdsByIndex, GetThreadIdsByIndex
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
req.alt-api: IDebugSystemObjects.GetThreadIdsByIndex,IDebugSystemObjects2.GetThreadIdsByIndex,IDebugSystemObjects3.GetThreadIdsByIndex,IDebugSystemObjects4.GetThreadIdsByIndex
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

# IDebugSystemObjects4::GetThreadIdsByIndex method



## -description
The <b>GetThreadIdsByIndex</b> method returns the engine and system thread IDs for the specified <a href="debugger.controlling_threads_and_processes#threads#threads">threads</a> in the current process.



## -syntax

````
HRESULT GetThreadIdsByIndex(
  [in]            ULONG  Start,
  [in]            ULONG  Count,
  [out, optional] PULONG Ids,
  [out, optional] PULONG SysIds
);
````


## -parameters

### -param Start [in]

Specifies the index of the first thread whose IDs are requested.


### -param Count [in]

Specifies the number of threads whose IDs are requested.


### -param Ids [out, optional]

Receives the engine thread IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG valuess.


### -param SysIds [out, optional]

Receives the system thread IDs.  If <i>SysIds</i> is <b>NULL</b>, this information is not returned; otherwise, <i>SysIds</i> is treated as an array of <i>Count</i> ULONG values.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
The index of the first thread is zero.  The index of the last thread is the number of threads returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547992">GetNumberThreads</a> minus one.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>