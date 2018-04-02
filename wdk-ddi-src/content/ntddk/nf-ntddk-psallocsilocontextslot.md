---
UID: NF:ntddk.PsAllocSiloContextSlot
title: PsAllocSiloContextSlot function
author: windows-driver-content
description: This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos. .
old-location: kernel\psallocsilocontextslot.htm
old-project: kernel
ms.assetid: 835446D1-EB41-47BC-AA0F-54A9C029EFFE
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsAllocSiloContextSlot, PsAllocSiloContextSlot routine [Kernel-Mode Driver Architecture], kernel.psallocsilocontextslot, ntddk/PsAllocSiloContextSlot
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PsAllocSiloContextSlot
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsAllocSiloContextSlot function


## -description


This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos. 


## -parameters




### -param Reserved [in]

This parameter is reserved for future use and <b>must be set to zero</b>. 

<div class="alert"><b>Warning</b>  Setting <i>Reserved</i> to a non-zero value causes the system to execute an <b>ASSERT</b> on a checked build.</div>
<div> </div>

### -param ReturnedContextSlot [out]

A pointer to a caller-allocated variable that receives the newly allocated slot index. This parameter is required and it cannot be <b>NULL</b>.


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
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>
</td>
<td width="60%">
There are no more slots available in the system. This is an error code.

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
 




## -remarks



Use of this API is uncommon because all silo monitors are assigned a storage slot when calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735079">PsRegisterSiloMonitor</a> routine.  That slot can be retrieved with the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735072">PsGetSiloMonitorContextSlot</a> routine and used by a driver for its context operations.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt735061">PsFreeSiloContextSlot</a>
 

 

