---
UID: NF:dbgeng.IDebugSystemObjects2.GetProcessIdByDataOffset
title: IDebugSystemObjects2::GetProcessIdByDataOffset method
author: windows-driver-content
description: The GetProcessIdByDataOffset method returns the engine process ID for the specified process. The process is specified by its data offset.
old-location: debugger\getprocessidbydataoffset.htm
old-project: debugger
ms.assetid: a2c094f4-f54d-4c3c-95e7-75df717db8cc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetProcessIdByDataOffset method [Windows Debugging], GetProcessIdByDataOffset method [Windows Debugging], IDebugSystemObjects interface, GetProcessIdByDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, GetProcessIdByDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, GetProcessIdByDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, GetProcessIdByDataOffset,IDebugSystemObjects2.GetProcessIdByDataOffset, IDebugSystemObjects interface [Windows Debugging], GetProcessIdByDataOffset method, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdByDataOffset method, IDebugSystemObjects2::GetProcessIdByDataOffset, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdByDataOffset method, IDebugSystemObjects3::GetProcessIdByDataOffset, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdByDataOffset method, IDebugSystemObjects4::GetProcessIdByDataOffset, IDebugSystemObjects::GetProcessIdByDataOffset, IDebugSystemObjects_8c7f276b-9a12-41ac-8c56-4e37b68d491d.xml, dbgeng/IDebugSystemObjects2::GetProcessIdByDataOffset, dbgeng/IDebugSystemObjects3::GetProcessIdByDataOffset, dbgeng/IDebugSystemObjects4::GetProcessIdByDataOffset, dbgeng/IDebugSystemObjects::GetProcessIdByDataOffset, debugger.getprocessidbydataoffset
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
-	IDebugSystemObjects.GetProcessIdByDataOffset
-	IDebugSystemObjects2.GetProcessIdByDataOffset
-	IDebugSystemObjects3.GetProcessIdByDataOffset
-	IDebugSystemObjects4.GetProcessIdByDataOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects2::GetProcessIdByDataOffset method


## -description


The <b>GetProcessIdByDataOffset</b> method returns the engine process ID for the specified process.  The process is specified by its data offset.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the data offset of the process.


### -param Id [out]

Receives the engine process ID for the process.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The current target is a kernel-mode target.  This method is currently not available in kernel-mode debugging.

</td>
</tr>
</table>
 




## -remarks



This method is currently not available in kernel-mode debugging.

In user-mode debugging, this method behaves the same as <a href="https://msdn.microsoft.com/library/windows/hardware/ff548150">GetProcessIdByPeb</a>.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



