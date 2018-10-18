---
UID: NF:ntddk.PsFreeSiloContextSlot
title: PsFreeSiloContextSlot function
author: windows-driver-content
description: This routine frees the specified slot and makes it available in the system. It undoes the effects of the PsAllocSiloContextSlot routine.
old-location: kernel\psfreesilocontextslot.htm
tech.root: kernel
ms.assetid: 659B92A6-8582-468F-8CDD-119832A95230
ms.date: 4/30/2018
ms.keywords: PsFreeSiloContextSlot, PsFreeSiloContextSlot routine [Kernel-Mode Driver Architecture], kernel.psfreesilocontextslot, ntddk/PsFreeSiloContextSlot
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsFreeSiloContextSlot
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsFreeSiloContextSlot function


## -description


This routine  frees the specified slot and makes it available in the system. It undoes the effects of the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt735056">PsAllocSiloContextSlot</a> routine.


## -parameters




### -param ContextSlot [in]

A slot allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735056">PsAllocSiloContextSlot</a> routine. 

<div class="alert"><b>Warning</b>  Setting this parameter to a slot that is still in use causes the system to execute bug check.</div>
<div> </div>

## -returns



The following NT status codes are returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The slot is not allocated in the system. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt735056">PsAllocSiloContextSlot</a>
 

 

