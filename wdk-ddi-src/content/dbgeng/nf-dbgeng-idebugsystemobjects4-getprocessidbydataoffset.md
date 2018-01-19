---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdByDataOffset
title: IDebugSystemObjects4::GetProcessIdByDataOffset method
author: windows-driver-content
description: The GetProcessIdByDataOffset method returns the engine process ID for the specified process. The process is specified by its data offset.
old-location: debugger\getprocessidbydataoffset.htm
old-project: debugger
ms.assetid: a2c094f4-f54d-4c3c-95e7-75df717db8cc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetProcessIdByDataOffset, GetProcessIdByDataOffset
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
req.alt-api: IDebugSystemObjects.GetProcessIdByDataOffset,IDebugSystemObjects2.GetProcessIdByDataOffset,IDebugSystemObjects3.GetProcessIdByDataOffset,IDebugSystemObjects4.GetProcessIdByDataOffset
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

# IDebugSystemObjects4::GetProcessIdByDataOffset method



## -description
The <b>GetProcessIdByDataOffset</b> method returns the engine process ID for the specified process.  The process is specified by its data offset.



## -syntax

````
HRESULT GetProcessIdByDataOffset(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space of the data offset of the process.


### -param Id [out]

Receives the engine process ID for the process.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The current target is a kernel-mode target.  This method is currently not available in kernel-mode debugging.

 


## -remarks
This method is currently not available in kernel-mode debugging.

In user-mode debugging, this method behaves the same as <a href="https://msdn.microsoft.com/library/windows/hardware/ff548150">GetProcessIdByPeb</a>.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>