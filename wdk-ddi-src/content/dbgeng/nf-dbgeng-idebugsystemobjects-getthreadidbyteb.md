---
UID: NF:dbgeng.IDebugSystemObjects.GetThreadIdByTeb
title: IDebugSystemObjects::GetThreadIdByTeb method
author: windows-driver-content
description: The GetThreadIdByTeb method returns the engine thread ID of the specified thread. The thread is specified by its thread environment block (TEB).
old-location: debugger\getthreadidbyteb.htm
old-project: debugger
ms.assetid: 64b98d8b-883b-4a2c-a5de-058bb3b732df
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetThreadIdByTeb method [Windows Debugging], GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects interface, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects2 interface, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects3 interface, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects4 interface, GetThreadIdByTeb,IDebugSystemObjects.GetThreadIdByTeb, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], GetThreadIdByTeb method, IDebugSystemObjects2 interface [Windows Debugging], GetThreadIdByTeb method, IDebugSystemObjects2::GetThreadIdByTeb, IDebugSystemObjects3 interface [Windows Debugging], GetThreadIdByTeb method, IDebugSystemObjects3::GetThreadIdByTeb, IDebugSystemObjects4 interface [Windows Debugging], GetThreadIdByTeb method, IDebugSystemObjects4::GetThreadIdByTeb, IDebugSystemObjects::GetThreadIdByTeb, IDebugSystemObjects_6f4062c3-c2ef-43bf-81c6-32103f37e793.xml, dbgeng/IDebugSystemObjects2::GetThreadIdByTeb, dbgeng/IDebugSystemObjects3::GetThreadIdByTeb, dbgeng/IDebugSystemObjects4::GetThreadIdByTeb, dbgeng/IDebugSystemObjects::GetThreadIdByTeb, debugger.getthreadidbyteb
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
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
-	IDebugSystemObjects.GetThreadIdByTeb
-	IDebugSystemObjects2.GetThreadIdByTeb
-	IDebugSystemObjects3.GetThreadIdByTeb
-	IDebugSystemObjects4.GetThreadIdByTeb
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects::GetThreadIdByTeb method


## -description


The <b>GetThreadIdByTeb</b> method returns the engine thread ID of the specified thread.  The thread is specified by its thread environment block (TEB).


## -syntax


````
HRESULT GetThreadIdByTeb(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````


## -parameters




### -param Offset [in]

Specifies the location of the thread's TEB.


### -param Id [out]

Receives the engine thread ID.


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
 




## -remarks



In kernel-mode debugging, this method returns the engine thread ID for the virtual thread representing the processor on which the specified thread is executing.  If the thread is not executing on a processor, this method will fail.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



