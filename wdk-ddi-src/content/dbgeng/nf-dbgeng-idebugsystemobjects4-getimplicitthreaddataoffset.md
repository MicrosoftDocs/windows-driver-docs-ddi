---
UID: NF:dbgeng.IDebugSystemObjects4.GetImplicitThreadDataOffset
title: IDebugSystemObjects4::GetImplicitThreadDataOffset method
author: windows-driver-content
description: The GetImplicitThreadDataOffset method returns the implicit thread for the current process.
old-location: debugger\getimplicitthreaddataoffset.htm
old-project: debugger
ms.assetid: fe7a1afe-dc87-412c-9e35-4a1af05f9474
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetImplicitThreadDataOffset, GetImplicitThreadDataOffset
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
req.alt-api: IDebugSystemObjects2.GetImplicitThreadDataOffset,IDebugSystemObjects3.GetImplicitThreadDataOffset,IDebugSystemObjects4.GetImplicitThreadDataOffset
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

# IDebugSystemObjects4::GetImplicitThreadDataOffset method



## -description
The <b>GetImplicitThreadDataOffset</b> method returns the implicit thread for the current process.



## -syntax

````
HRESULT GetImplicitThreadDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

Receives the location in the target's memory address space of the data structure of the system thread that is the implicit thread for the current process.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, the data structure is the KTHREAD structure for the process.

In user-mode debugging, the data structure is the thread environment block (TEB) for the process.

For more information about the implicit thread, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KTHREAD structure and TEB, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>