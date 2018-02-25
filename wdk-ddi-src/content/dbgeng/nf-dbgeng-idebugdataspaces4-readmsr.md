---
UID: NF:dbgeng.IDebugDataSpaces4.ReadMsr
title: IDebugDataSpaces4::ReadMsr method
author: windows-driver-content
description: The ReadMsr method reads a specified Model-Specific Register (MSR).
old-location: debugger\readmsr2.htm
old-project: debugger
ms.assetid: 3ffe53d9-ea57-4561-a889-e6369ef0d5d3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 4, :, D, I, IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], ReadMsr method, IDebugDataSpaces2, IDebugDataSpaces2 interface [Windows Debugging], ReadMsr method, IDebugDataSpaces2::ReadMsr, IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], ReadMsr method, IDebugDataSpaces3::ReadMsr, IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], ReadMsr method, IDebugDataSpaces4::ReadMsr, IDebugDataSpaces::ReadMsr, IDebugDataSpaces_ad5999a9-949f-4771-b0b9-16fa1b79ac10.xml, M, R, ReadMsr method [Windows Debugging], ReadMsr method [Windows Debugging], IDebugDataSpaces interface, ReadMsr method [Windows Debugging], IDebugDataSpaces2 interface, ReadMsr method [Windows Debugging], IDebugDataSpaces3 interface, ReadMsr method [Windows Debugging], IDebugDataSpaces4 interface, ReadMsr,IDebugDataSpaces.ReadMsr, ReadMsr,IDebugDataSpaces2.ReadMsr, ReadMsr,IDebugDataSpaces3.ReadMsr, ReadMsr,IDebugDataSpaces4.ReadMsr, S, a, b, c, d, dbgeng/IDebugDataSpaces2::ReadMsr, dbgeng/IDebugDataSpaces3::ReadMsr, dbgeng/IDebugDataSpaces4::ReadMsr, dbgeng/IDebugDataSpaces::ReadMsr, debugger.readmsr2, e, g, p, r, s, t, u"
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
-	IDebugDataSpaces.ReadMsr
-	IDebugDataSpaces2.ReadMsr
-	IDebugDataSpaces3.ReadMsr
-	IDebugDataSpaces4.ReadMsr
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadMsr method


## -description


The <b>ReadMsr</b> method reads a specified Model-Specific Register (MSR).


## -syntax


````
HRESULT ReadMsr(
  [in]  ULONG    Msr,
  [out] PULONG64 Value
);
````


## -parameters




### -param Msr [in]

Specifies the MSR address.


### -param Value [out]

Receives the value of the MSR.


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



