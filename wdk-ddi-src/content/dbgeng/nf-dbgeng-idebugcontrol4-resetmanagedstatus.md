---
UID: NF:dbgeng.IDebugControl4.ResetManagedStatus
title: IDebugControl4::ResetManagedStatus method
author: windows-driver-content
description: Clears and reinitializes the engine's managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_resetmanagedstatus.htm
old-project: debugger
ms.assetid: 6A9F8963-54F2-4AD7-AB98-C3215E1F7839
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl4, IDebugControl4 interface [Windows Debugging], ResetManagedStatus method, IDebugControl4::ResetManagedStatus, ResetManagedStatus method [Windows Debugging], ResetManagedStatus method [Windows Debugging], IDebugControl4 interface, ResetManagedStatus,IDebugControl4.ResetManagedStatus, dbgeng/IDebugControl4::ResetManagedStatus, debugger.idebugcontrol4_resetmanagedstatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.ResetManagedStatus
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::ResetManagedStatus method


## -description


    Clears and reinitializes the engine's
    managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).


## -parameters




### -param Flags [in]

Flags for the debugging API.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

    Managed debugging support relies on debugging
    functionality provided by the CLR.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

