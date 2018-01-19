---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdByPeb
title: IDebugSystemObjects4::GetProcessIdByPeb method
author: windows-driver-content
description: The GetProcessIdByPeb method returns the engine process ID for the specified process. The process is specified by its process environment block (PEB).
old-location: debugger\getprocessidbypeb.htm
old-project: debugger
ms.assetid: 2ee2b610-30c7-4932-b8f6-df5040a5bad8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetProcessIdByPeb, GetProcessIdByPeb
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
req.alt-api: IDebugSystemObjects.GetProcessIdByPeb,IDebugSystemObjects2.GetProcessIdByPeb,IDebugSystemObjects3.GetProcessIdByPeb,IDebugSystemObjects4.GetProcessIdByPeb
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

# IDebugSystemObjects4::GetProcessIdByPeb method



## -description
The <b>GetProcessIdByPeb</b> method returns the engine process ID for the specified process.  The process is specified by its process environment block (PEB).



## -syntax

````
HRESULT GetProcessIdByPeb(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space of the PEB of the process whose process ID is requested.


### -param Id [out]

Receives the engine process ID.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The target is a kernel-mode target.  This method is currently not available in kernel-mode debugging.

 


## -remarks
This method is not available in kernel-mode debugging.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>