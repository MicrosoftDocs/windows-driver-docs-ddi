---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadTeb
title: IDebugSystemObjects4::GetCurrentThreadTeb method
author: windows-driver-content
description: The GetCurrentThreadTeb method returns the location of the thread environment block (TEB) for the current thread.
old-location: debugger\getcurrentthreadteb.htm
old-project: debugger
ms.assetid: f5acd64c-c5a8-4977-8059-cc0bd12ef0c0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentThreadTeb, GetCurrentThreadTeb
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
req.alt-api: IDebugSystemObjects.GetCurrentThreadTeb,IDebugSystemObjects2.GetCurrentThreadTeb,IDebugSystemObjects3.GetCurrentThreadTeb,IDebugSystemObjects4.GetCurrentThreadTeb
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

# IDebugSystemObjects4::GetCurrentThreadTeb method



## -description
The <b>GetCurrentThreadTeb</b> method returns the location of the thread environment block (TEB) for the current thread.



## -syntax

````
HRESULT GetCurrentThreadTeb(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

Receives the location in the target's virtual address space of the TEB for the current thread.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In user-mode debugging, this method provides the same information as <a href="https://msdn.microsoft.com/library/windows/hardware/ff545894">GetCurrentThreadDataOffset</a>.

In kernel-mode debugging, the location returned is of the TEB structure of the system thread that was executing on the processor represented by the current thread when the last event occurred.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the TEB structure, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>