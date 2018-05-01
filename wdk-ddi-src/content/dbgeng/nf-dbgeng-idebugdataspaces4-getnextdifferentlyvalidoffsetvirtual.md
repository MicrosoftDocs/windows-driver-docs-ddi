---
UID: NF:dbgeng.IDebugDataSpaces4.GetNextDifferentlyValidOffsetVirtual
title: IDebugDataSpaces4::GetNextDifferentlyValidOffsetVirtual
author: windows-driver-content
description: The GetNextDifferentlyValidOffsetVirtual method returns the offset of the next address whose validity might be different from the validity of the specified address.
old-location: debugger\getnextdifferentlyvalidoffsetvirtual.htm
old-project: debugger
ms.assetid: 1f55cc21-606d-4c7c-8650-51cb686700b3
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetNextDifferentlyValidOffsetVirtual, GetNextDifferentlyValidOffsetVirtual method [Windows Debugging], GetNextDifferentlyValidOffsetVirtual method [Windows Debugging],IDebugDataSpaces4 interface, IDebugDataSpaces4 interface [Windows Debugging],GetNextDifferentlyValidOffsetVirtual method, IDebugDataSpaces4.GetNextDifferentlyValidOffsetVirtual, IDebugDataSpaces4::GetNextDifferentlyValidOffsetVirtual, IDebugDataSpaces_9308b61e-2e9a-4e17-a918-8af4c1b132b8.xml, dbgeng/IDebugDataSpaces4::GetNextDifferentlyValidOffsetVirtual, debugger.getnextdifferentlyvalidoffsetvirtual
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
-	IDebugDataSpaces4.GetNextDifferentlyValidOffsetVirtual
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces4::GetNextDifferentlyValidOffsetVirtual


## -description


The <b>GetNextDifferentlyValidOffsetVirtual</b> method returns the offset of the next address whose validity might be different from the validity of the specified address.


## -parameters




### -param Offset [in]

Specifies a start address.  The address returned in <i>NextOffset</i> will be the next address whose validity might be defined differently from this one.


### -param NextOffset [out]

Receives the address of the next address whose validity might be defined differently from the address in <i>Offset</i>.


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
 




## -remarks



The size of regions of validity depends on the target.  For example, in live user-mode debugging sessions, where virtual address validity changes from page to page, <i>NextOffset</i> will receive the address of the next page.  In user-mode dump files the validity can change from byte to byte.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549471">GetValidRegionVirtual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>
 

 

