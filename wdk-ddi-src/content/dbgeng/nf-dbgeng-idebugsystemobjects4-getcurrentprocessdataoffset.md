---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessDataOffset
title: IDebugSystemObjects4::GetCurrentProcessDataOffset method
author: windows-driver-content
description: The GetCurrentProcessDataOffset method returns the location of the system data structure describing the current process.
old-location: debugger\getcurrentprocessdataoffset.htm
old-project: debugger
ms.assetid: a71190ac-0368-40bd-a19d-82a27986a9b3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentProcessDataOffset, GetCurrentProcessDataOffset
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
req.alt-api: IDebugSystemObjects.GetCurrentProcessDataOffset,IDebugSystemObjects2.GetCurrentProcessDataOffset,IDebugSystemObjects3.GetCurrentProcessDataOffset,IDebugSystemObjects4.GetCurrentProcessDataOffset
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

# IDebugSystemObjects4::GetCurrentProcessDataOffset method



## -description
The <b>GetCurrentProcessDataOffset</b> method returns the location of the system data structure describing the current process.



## -syntax

````
HRESULT GetCurrentProcessDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

Receives the location in the target's virtual address space of the system data structure describing the current process.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In user-mode debugging, the location returned is of the process environment block (PEB) for the current process.  This is the same location returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545839">GetCurrentProcessPeb</a>.

In kernel-mode debugging, the location returned is of the KPROCESS structure for the system process in which the last event occurred.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details about the PEB and KPROCESS structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>