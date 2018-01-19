---
UID: NF:dbgeng.IDebugSystemObjects4.SetImplicitProcessDataOffset
title: IDebugSystemObjects4::SetImplicitProcessDataOffset method
author: windows-driver-content
description: The SetImplicitProcessDataOffset method sets the implicit process for the current target.
old-location: debugger\setimplicitprocessdataoffset.htm
old-project: debugger
ms.assetid: 2a09341d-a580-4817-9103-29d8c36b81e3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitProcessDataOffset, SetImplicitProcessDataOffset
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
req.alt-api: IDebugSystemObjects2.SetImplicitProcessDataOffset,IDebugSystemObjects3.SetImplicitProcessDataOffset,IDebugSystemObjects4.SetImplicitProcessDataOffset
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

# IDebugSystemObjects4::SetImplicitProcessDataOffset method



## -description
The <b>SetImplicitProcessDataOffset</b> method sets the implicit process for the current target.



## -syntax

````
HRESULT SetImplicitProcessDataOffset(
  [in] ULONG64 Offset
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's memory address space of the data structure of the system process that is to become the implicit process for the current target.  If this is zero, the implicit process for the current target is set to the default implicit process.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
In kernel-mode debugging, the data structure is the KPROCESS structure for the process.

In user-mode debugging, the data structure is the process environment block (PEB) for the process.

For more information about the current implicit process, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>