---
UID: NF:dbgeng.IDebugSystemObjects4.SetImplicitThreadDataOffset
title: IDebugSystemObjects4::SetImplicitThreadDataOffset method
author: windows-driver-content
description: The SetImplicitThreadDataOffset method sets the implicit thread for the current process.
old-location: debugger\setimplicitthreaddataoffset.htm
old-project: debugger
ms.assetid: 1562a2f4-0eea-44fd-b350-ccc17d8cd65e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
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
req.alt-api: IDebugSystemObjects2.SetImplicitThreadDataOffset,IDebugSystemObjects3.SetImplicitThreadDataOffset,IDebugSystemObjects4.SetImplicitThreadDataOffset
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

# IDebugSystemObjects4::SetImplicitThreadDataOffset method



## -description
The <b>SetImplicitThreadDataOffset</b> method sets the implicit thread for the current process.



## -syntax

````
HRESULT SetImplicitThreadDataOffset(
  [in] ULONG64 Offset
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's memory address space of the data structure of the system thread that is to become the implicit thread for the current process.  If this is zero, the implicit thread for the current process is set to the default implicit thread.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, the data structure is the KTHREAD structure for the process.

In user-mode debugging, the data structure is the thread environment block (TEB) for the process.

For more information about the current implicit thread, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KTHREAD structure and TEB, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>