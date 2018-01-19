---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessPeb
title: IDebugSystemObjects4::GetCurrentProcessPeb method
author: windows-driver-content
description: The GetCurrentProcessPeb method returns the process environment block (PEB) of the current process.
old-location: debugger\getcurrentprocesspeb.htm
old-project: debugger
ms.assetid: fa1e2915-3cb5-4634-a8fb-0d2d565c1c00
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentProcessPeb, GetCurrentProcessPeb
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
req.alt-api: IDebugSystemObjects.GetCurrentProcessPeb,IDebugSystemObjects2.GetCurrentProcessPeb,IDebugSystemObjects3.GetCurrentProcessPeb,IDebugSystemObjects4.GetCurrentProcessPeb
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

# IDebugSystemObjects4::GetCurrentProcessPeb method



## -description
The <b>GetCurrentProcessPeb</b> method returns the process environment block (PEB) of the current process.



## -syntax

````
HRESULT GetCurrentProcessPeb(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

Receives the location in the target's virtual address space of the PEB of the current process.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In user-mode debugging, this method provides the same information as <a href="https://msdn.microsoft.com/library/windows/hardware/ff545787">GetCurrentProcessDataOffset</a>.

In kernel-mode debugging, the location returned is that of the PEB structure for the system process in which the last event occurred.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>