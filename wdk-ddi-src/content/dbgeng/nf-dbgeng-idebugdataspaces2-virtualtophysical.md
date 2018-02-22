---
UID: NF:dbgeng.IDebugDataSpaces2.VirtualToPhysical
title: IDebugDataSpaces2::VirtualToPhysical method
author: windows-driver-content
description: The VirtualToPhysical method translates a location in the target's virtual address space into a physical memory address.
old-location: debugger\virtualtophysical.htm
old-project: Debugger
ms.assetid: e0b7bd4c-cb3f-4bc3-8359-241c9a245204
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugDataSpaces4 interface [Windows Debugging], VirtualToPhysical method, VirtualToPhysical method [Windows Debugging], IDebugDataSpaces2 interface, VirtualToPhysical method [Windows Debugging], IDebugDataSpaces3 interface [Windows Debugging], VirtualToPhysical method, IDebugDataSpaces4::VirtualToPhysical, VirtualToPhysical, IDebugDataSpaces3::VirtualToPhysical, IDebugDataSpaces2, IDebugDataSpaces2::VirtualToPhysical, IDebugDataSpaces2 interface [Windows Debugging], VirtualToPhysical method, VirtualToPhysical method [Windows Debugging], IDebugDataSpaces3 interface, dbgeng/IDebugDataSpaces3::VirtualToPhysical, dbgeng/IDebugDataSpaces4::VirtualToPhysical, VirtualToPhysical method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces_56267474-49c4-446c-83eb-3e4eb2e92734.xml, dbgeng/IDebugDataSpaces2::VirtualToPhysical, debugger.virtualtophysical
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
-	IDebugDataSpaces2.VirtualToPhysical
-	IDebugDataSpaces3.VirtualToPhysical
-	IDebugDataSpaces4.VirtualToPhysical
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces2::VirtualToPhysical method


## -description


The <b>VirtualToPhysical</b> method translates a location in the target's virtual address space into a physical memory address.


## -syntax


````
HRESULT VirtualToPhysical(
  [in]  ULONG64  Virtual,
  [out] PULONG64 Physical
);
````


## -parameters




### -param Virtual [in]

Specifies the location in the target's virtual address space to translate.


### -param Physical [out]

Receives the physical memory address.


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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_PAGEFILE)</b></dt>
</dl>
</td>
<td width="60%">
No physical page containing the specified address could be found.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method is only available in kernel-mode debugging.



