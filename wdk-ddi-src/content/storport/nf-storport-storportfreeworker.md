---
UID: NF:storport.StorPortFreeWorker
title: StorPortFreeWorker function
author: windows-driver-content
description: Frees a Storport work item previously allocated by the StorPortInitializeWorker routine.
old-location: storage\storportfreeworker.htm
tech.root: storage
ms.assetid: 90BD61C8-322B-48D5-83E0-7204E3DC4423
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortFreeWorker, StorPortFreeWorker routine [Storage Devices], storage.storportfreeworker, storport/StorPortFreeWorker
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
-	StorPortFreeWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortFreeWorker function


## -description


Frees a Storport work item previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a> routine.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Worker

<p>A pointer to an opaque buffer for the work item context returned by <a href="https://msdn.microsoft.com/library/Hh451486(v=VS.85).aspx"><b>StorPortInitializeWorker</b></a>.</p>




#### - WorkItem [in]

A pointer to an opaque buffer for the work item context returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a>.


## -returns



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a> routine returns one of these status codes:

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
Either <i>HwDeviceExtension</i> or <i>WorkItem</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The work item is currently queued for processing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The work item was successfully freed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The work item is already free.

</td>
</tr>
</table>
 




## -remarks



Miniports should call <b>StorPortFreeWorker</b> whenever a work item is no longer needed or when the miniport receives a PnP SRB notification  that the adapter is removed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451509">StorPortQueueWorkItem</a>
 

 

