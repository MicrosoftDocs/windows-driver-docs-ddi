---
UID: NF:dbgeng.IDebugDataSpaces3.WriteMsr
title: IDebugDataSpaces3::WriteMsr method
author: windows-driver-content
description: The WriteMsr method writes a value to the specified Model-Specific Register (MSR).
old-location: debugger\writemsr2.htm
old-project: debugger
ms.assetid: c9838b9e-b390-455d-98d6-249a49c9165d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging], WriteMsr method, IDebugDataSpaces2 interface [Windows Debugging], WriteMsr method, IDebugDataSpaces2::WriteMsr, IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], WriteMsr method, IDebugDataSpaces3::WriteMsr, IDebugDataSpaces4 interface [Windows Debugging], WriteMsr method, IDebugDataSpaces4::WriteMsr, IDebugDataSpaces::WriteMsr, IDebugDataSpaces_b0b0220e-66d2-4d96-b4bf-3016b0ed677c.xml, WriteMsr method [Windows Debugging], WriteMsr method [Windows Debugging], IDebugDataSpaces interface, WriteMsr method [Windows Debugging], IDebugDataSpaces2 interface, WriteMsr method [Windows Debugging], IDebugDataSpaces3 interface, WriteMsr method [Windows Debugging], IDebugDataSpaces4 interface, WriteMsr,IDebugDataSpaces3.WriteMsr, dbgeng/IDebugDataSpaces2::WriteMsr, dbgeng/IDebugDataSpaces3::WriteMsr, dbgeng/IDebugDataSpaces4::WriteMsr, dbgeng/IDebugDataSpaces::WriteMsr, debugger.writemsr2
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
-	Dbgeng.h
api_name:
-	IDebugDataSpaces.WriteMsr
-	IDebugDataSpaces2.WriteMsr
-	IDebugDataSpaces3.WriteMsr
-	IDebugDataSpaces4.WriteMsr
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces3::WriteMsr method


## -description


The <b>WriteMsr</b> method writes a value to the specified Model-Specific Register (MSR).


## -parameters




### -param Msr

Specifies the MSR address.


### -param Value

Specifies the value to write to the MSR.


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
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method is only available in kernel-mode debugging.

For details on the addresses and values of MSRs, see the processor documentation.



