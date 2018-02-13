---
UID: NF:dbgeng.IDebugSystemObjects3.GetImplicitThreadDataOffset
title: IDebugSystemObjects3::GetImplicitThreadDataOffset method
author: windows-driver-content
description: The GetImplicitThreadDataOffset method returns the implicit thread for the current process.
old-location: debugger\getimplicitthreaddataoffset.htm
old-project: debugger
ms.assetid: fe7a1afe-dc87-412c-9e35-4a1af05f9474
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects2::GetImplicitThreadDataOffset, GetImplicitThreadDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, GetImplicitThreadDataOffset, IDebugSystemObjects2 interface [Windows Debugging], GetImplicitThreadDataOffset method, GetImplicitThreadDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, dbgeng/IDebugSystemObjects2::GetImplicitThreadDataOffset, GetImplicitThreadDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects4::GetImplicitThreadDataOffset, dbgeng/IDebugSystemObjects3::GetImplicitThreadDataOffset, IDebugSystemObjects2, IDebugSystemObjects3 interface [Windows Debugging], GetImplicitThreadDataOffset method, IDebugSystemObjects3::GetImplicitThreadDataOffset, IDebugSystemObjects3, IDebugSystemObjects_fd957a10-62ec-464c-b5d0-c1b36a13013f.xml, IDebugSystemObjects4 interface [Windows Debugging], GetImplicitThreadDataOffset method, debugger.getimplicitthreaddataoffset, GetImplicitThreadDataOffset method [Windows Debugging], IDebugSystemObjects4::GetImplicitThreadDataOffset
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects2.GetImplicitThreadDataOffset
-	IDebugSystemObjects3.GetImplicitThreadDataOffset
-	IDebugSystemObjects4.GetImplicitThreadDataOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects3::GetImplicitThreadDataOffset method


## -description


The <b>GetImplicitThreadDataOffset</b> method returns the implicit thread for the current process.


## -syntax


````
HRESULT GetImplicitThreadDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters




### -param Offset [out]

Receives the location in the target's memory address space of the data structure of the system thread that is the implicit thread for the current process.


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



In kernel-mode debugging, the data structure is the KTHREAD structure for the process.

In user-mode debugging, the data structure is the thread environment block (TEB) for the process.

For more information about the implicit thread, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KTHREAD structure and TEB, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



