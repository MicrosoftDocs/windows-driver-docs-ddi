---
UID: NF:storport.StorPortFreeTimer
title: StorPortFreeTimer function
author: windows-driver-content
description: Frees a Storport timer context object previously created by the StorPortInitializeTimer routine.
old-location: storage\storportfreetimer.htm
old-project: storage
ms.assetid: AF6B1693-6242-4F09-8226-472E75B809F3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortFreeTimer, StorPortFreeTimer routine [Storage Devices], storage.storportfreetimer, storport/StorPortFreeTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortFreeTimer
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortFreeTimer function


## -description


Frees a Storport timer context object previously created by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451483">StorPortInitializeTimer</a> routine.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param TimerHandle [in]

A pointer to an opaque buffer for the timer context returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451483">StorPortInitializeTimer</a>.


## -returns



The <b>StorPortFreeTimer</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
Current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>TimerHandle</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to free the timer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The timer was successfully freed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The timer is already free.

</td>
</tr>
</table>
 




## -remarks



Miniports should call <b>StorPortFreeTimer</b> whenever a work item is no longer needed or when the miniport receives a PnP SRB notification  that the adapter is removed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557365">HwStorAdapterControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451483">StorPortInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451511">StorPortRequestTimer</a>
 

 

