---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessUpTime
title: IDebugSystemObjects4::GetCurrentProcessUpTime method
author: windows-driver-content
description: The GetCurrentProcessUpTime method returns the length of time the current process has been running.
old-location: debugger\getcurrentprocessuptime.htm
old-project: debugger
ms.assetid: 6c6f3824-5e04-45df-8128-f3778aaa3636
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentProcessUpTime, GetCurrentProcessUpTime
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
req.alt-api: IDebugSystemObjects2.GetCurrentProcessUpTime,IDebugSystemObjects3.GetCurrentProcessUpTime,IDebugSystemObjects4.GetCurrentProcessUpTime
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

# IDebugSystemObjects4::GetCurrentProcessUpTime method



## -description
The <b>GetCurrentProcessUpTime</b> method returns the length of time the current process has been running.



## -syntax

````
HRESULT GetCurrentProcessUpTime(
  [out] PULONG UpTime
);
````


## -parameters

### -param UpTime [out]

Receives the number of seconds the current process has been running.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
