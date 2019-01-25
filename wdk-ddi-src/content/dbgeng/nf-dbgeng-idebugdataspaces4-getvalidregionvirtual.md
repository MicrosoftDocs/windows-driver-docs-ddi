---
UID: NF:dbgeng.IDebugDataSpaces4.GetValidRegionVirtual
title: IDebugDataSpaces4::GetValidRegionVirtual (dbgeng.h)
description: The GetValidRegionVirtual method locates the first valid region of memory in a specified memory range.
old-location: debugger\getvalidregionvirtual.htm
tech.root: debugger
ms.assetid: b580c2ef-94f9-4738-bd00-0d5a4753f71a
ms.date: 05/03/2018
ms.keywords: GetValidRegionVirtual, GetValidRegionVirtual method [Windows Debugging], GetValidRegionVirtual method [Windows Debugging],IDebugDataSpaces4 interface, IDebugDataSpaces4 interface [Windows Debugging],GetValidRegionVirtual method, IDebugDataSpaces4.GetValidRegionVirtual, IDebugDataSpaces4::GetValidRegionVirtual, IDebugDataSpaces_594749e6-fa97-49fb-aabe-643ac4415ed9.xml, dbgeng/IDebugDataSpaces4::GetValidRegionVirtual, debugger.getvalidregionvirtual
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
-	IDebugDataSpaces4.GetValidRegionVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces4::GetValidRegionVirtual


## -description


The <b>GetValidRegionVirtual</b> method locates the first valid region of memory in a specified memory range.


## -parameters




### -param Base [in]

Specifies the address of the beginning of the memory range to search for valid memory.


### -param Size [in]

Specifies the size, in bytes, of the memory range to search.


### -param ValidBase [out]

Receives the address of the beginning of the found valid memory.


### -param ValidSize [out]

Receives the size, in bytes, of the valid memory.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547847">GetNextDifferentlyValidOffsetVirtual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>
 

 

