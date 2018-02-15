---
UID: NF:dbgeng.IDebugDataSpaces3.CheckLowMemory
title: IDebugDataSpaces3::CheckLowMemory method
author: windows-driver-content
description: The CheckLowMemory method checks for memory corruption in the low 4 GB of memory.
old-location: debugger\checklowmemory.htm
old-project: debugger
ms.assetid: b7e3bb5c-d4c7-469e-aa2d-fa9a98706c2f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging], CheckLowMemory method, dbgeng/IDebugDataSpaces::CheckLowMemory, CheckLowMemory method [Windows Debugging], CheckLowMemory method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces3::CheckLowMemory, IDebugDataSpaces3 interface [Windows Debugging], CheckLowMemory method, dbgeng/IDebugDataSpaces3::CheckLowMemory, dbgeng/IDebugDataSpaces2::CheckLowMemory, IDebugDataSpaces2, dbgeng/IDebugDataSpaces4::CheckLowMemory, IDebugDataSpaces4::CheckLowMemory, CheckLowMemory, CheckLowMemory method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces2 interface [Windows Debugging], CheckLowMemory method, CheckLowMemory method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces4 interface [Windows Debugging], CheckLowMemory method, IDebugDataSpaces3, debugger.checklowmemory, IDebugDataSpaces_6682f39e-295a-4dae-b8a3-d83b1d5e41be.xml, IDebugDataSpaces, IDebugDataSpaces::CheckLowMemory, CheckLowMemory method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces2::CheckLowMemory
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
-	Dbgeng.h
apiname:
-	IDebugDataSpaces.CheckLowMemory
-	IDebugDataSpaces2.CheckLowMemory
-	IDebugDataSpaces3.CheckLowMemory
-	IDebugDataSpaces4.CheckLowMemory
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugDataSpaces3::CheckLowMemory method


## -description


The <b>CheckLowMemory</b> method checks for memory corruption in the low 4 GB of memory.


## -syntax


````
HRESULT CheckLowMemory();
````


## -parameters






## -returns



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
No corruption was found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FACILITY_NT_BIT |<i>Page</i></b></dt>
</dl>
</td>
<td width="60%">
Corruption was found on the memory page <i>Page</i>.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method is only available in <a href="https://msdn.microsoft.com/93b65114-f680-41f7-b754-699f773955ba">kernel-mode debugging</a>, and is only useful when the <a href="https://msdn.microsoft.com/93b65114-f680-41f7-b754-699f773955ba">kernel</a> was booted using the <b>/nolowmem</b> option.

When the kernel is booted with the <b>/nolowmem</b> option, the kernel, drivers, operating system and applications are loaded in memory above 4 GB, while the low 4 GB of memory is filled with a unique pattern.  The <b>CheckLowMemory</b> method checks this pattern for corruption.

This may be used to verify that a driver behaves well when using physical addresses greater than 32 bits in length.  See <i>Physical Address Extension (PAE)</i>, <b>/pae</b>, and <b>/nolowmem</b> in the Windows Driver Kit.



