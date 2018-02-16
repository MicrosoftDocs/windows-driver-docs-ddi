---
UID: NF:dbgeng.IDebugSystemObjects4.GetImplicitProcessDataOffset
title: IDebugSystemObjects4::GetImplicitProcessDataOffset method
author: windows-driver-content
description: The GetImplicitProcessDataOffset method returns the implicit process for the current target.
old-location: debugger\getimplicitprocessdataoffset.htm
old-project: debugger
ms.assetid: 20a11f3b-cc49-4080-ac4c-b8e18d4b2f73
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects2::GetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects4::GetImplicitProcessDataOffset, IDebugSystemObjects_3ec83d96-a7ff-4767-be21-b822c45ae01e.xml, GetImplicitProcessDataOffset, GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, dbgeng/IDebugSystemObjects2::GetImplicitProcessDataOffset, debugger.getimplicitprocessdataoffset, dbgeng/IDebugSystemObjects3::GetImplicitProcessDataOffset, GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects4 interface [Windows Debugging], GetImplicitProcessDataOffset method, IDebugSystemObjects2 interface [Windows Debugging], GetImplicitProcessDataOffset method, GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging], GetImplicitProcessDataOffset method, IDebugSystemObjects2, IDebugSystemObjects3::GetImplicitProcessDataOffset, IDebugSystemObjects3, IDebugSystemObjects4::GetImplicitProcessDataOffset, IDebugSystemObjects4
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
-	IDebugSystemObjects2.GetImplicitProcessDataOffset
-	IDebugSystemObjects3.GetImplicitProcessDataOffset
-	IDebugSystemObjects4.GetImplicitProcessDataOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
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



In kernel-mode debugging, the data structure is the KPROCESS structure for the process.

In user-mode debugging, the data structure is the process environment block (PEB) for the process.

For more information about the implicit process, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



