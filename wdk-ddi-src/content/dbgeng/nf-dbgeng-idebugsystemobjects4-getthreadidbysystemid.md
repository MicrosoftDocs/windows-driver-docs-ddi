---
UID: NF:dbgeng.IDebugSystemObjects4.GetThreadIdBySystemId
title: IDebugSystemObjects4::GetThreadIdBySystemId method
author: windows-driver-content
description: The GetThreadIdBySystemId method returns the engine thread ID for the specified thread. The thread is specified by its system thread ID.
old-location: debugger\getthreadidbysystemid.htm
old-project: debugger
ms.assetid: 2dcb7703-df66-4795-bf59-d0851c4ccf0f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetThreadIdBySystemId, GetThreadIdBySystemId
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
req.alt-api: IDebugSystemObjects.GetThreadIdBySystemId,IDebugSystemObjects2.GetThreadIdBySystemId,IDebugSystemObjects3.GetThreadIdBySystemId,IDebugSystemObjects4.GetThreadIdBySystemId
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

# IDebugSystemObjects4::GetThreadIdBySystemId method



## -description
The <b>GetThreadIdBySystemId</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system thread ID.



## -syntax

````
HRESULT GetThreadIdBySystemId(
  [in]  ULONG  SysId,
  [out] PULONG Id
);
````


## -parameters

### -param SysId [in]

Specifies the system thread ID.


### -param Id [out]

Receives the engine thread ID.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The target is a kernel-mode target.

 


## -remarks
This method is only available in user-mode debugging.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>