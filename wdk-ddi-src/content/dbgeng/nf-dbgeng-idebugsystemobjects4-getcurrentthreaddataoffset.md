---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadDataOffset
title: IDebugSystemObjects4::GetCurrentThreadDataOffset method
author: windows-driver-content
description: The GetCurrentThreadDataOffset method returns the location of the system data structure for the current thread.
old-location: debugger\getcurrentthreaddataoffset.htm
old-project: debugger
ms.assetid: 7837c049-fdca-4f90-9f38-2ec91ed8703b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentThreadDataOffset, GetCurrentThreadDataOffset
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
req.alt-api: IDebugSystemObjects.GetCurrentThreadDataOffset,IDebugSystemObjects2.GetCurrentThreadDataOffset,IDebugSystemObjects3.GetCurrentThreadDataOffset,IDebugSystemObjects4.GetCurrentThreadDataOffset
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

# IDebugSystemObjects4::GetCurrentThreadDataOffset method



## -description
The <b>GetCurrentThreadDataOffset</b> method returns the location of the system data structure for the current thread.



## -syntax

````
HRESULT GetCurrentThreadDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

Receives the location of the system data structure for the current thread.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In user-mode debugging, the location returned is of the thread environment block (TEB) for the current thread.  This is the same location returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546549">GetCurrentThreadTeb</a>.

In kernel-mode debugging, the location returned is of the KTHREAD structure of the system thread that was executing on the processor represented by the current thread when the last event occurred.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KTHREAD and TEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>