---
UID: NF:storport.StorPortGetDataInBufferScatterGatherList
title: StorPortGetDataInBufferScatterGatherList function
author: windows-driver-content
description: Returns the scatter-gather list associated with the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbufferscattergatherlist.htm
old-project: storage
ms.assetid: 015592AE-4AF6-48C8-BF79-6B22A6FCAB98
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetDataInBufferScatterGatherList, StorPortGetDataInBufferScatterGatherList routine [Storage Devices], storage.storportgetdatainbufferscattergatherlist, storport/StorPortGetDataInBufferScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Storport.lib
req.dll: 
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortGetDataInBufferScatterGatherList
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetDataInBufferScatterGatherList function


## -description


Returns the scatter-gather list associated with the input data buffer  of a SCSI request block (SRB).


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The request block to containing the input data buffer for the scatter-gather list.


### -param SgList [out]

A pointer to  an scatter-gather list structure address to receive the scatter-gather list for the input data buffer in <i>Srb</i>.


## -returns



A status value indicating the result of the notification. This can be one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The scatter-gather list for <i>Srb</i> was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer value in <i>SgList</i> is NULL.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj553718">StorPortGetDataInBufferMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj553720">StorPortGetDataInBufferSystemAddress</a>
 

 

