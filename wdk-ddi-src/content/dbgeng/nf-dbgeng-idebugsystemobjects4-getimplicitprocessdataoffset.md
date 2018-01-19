---
UID: NF:dbgeng.IDebugSystemObjects4.GetImplicitProcessDataOffset
title: IDebugSystemObjects4::GetImplicitProcessDataOffset method
author: windows-driver-content
description: The GetImplicitProcessDataOffset method returns the implicit process for the current target.
old-location: debugger\getimplicitprocessdataoffset.htm
old-project: debugger
ms.assetid: 20a11f3b-cc49-4080-ac4c-b8e18d4b2f73
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetImplicitProcessDataOffset, GetImplicitProcessDataOffset
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
req.alt-api: IDebugSystemObjects2.GetImplicitProcessDataOffset,IDebugSystemObjects3.GetImplicitProcessDataOffset,IDebugSystemObjects4.GetImplicitProcessDataOffset
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

# IDebugSystemObjects4::GetImplicitProcessDataOffset method



## -description
The <b>GetImplicitProcessDataOffset</b> method returns the implicit process for the current target.



## -syntax

````
HRESULT GetImplicitProcessDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

Receives the location in the target's memory address space of the data structure of the system process that is the implicit process for the current target.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, the data structure is the KPROCESS structure for the process.

In user-mode debugging, the data structure is the process environment block (PEB) for the process.

For more information about the implicit process, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>