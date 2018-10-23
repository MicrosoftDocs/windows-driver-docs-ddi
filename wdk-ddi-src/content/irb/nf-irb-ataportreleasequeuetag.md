---
UID: NF:irb.AtaPortReleaseQueueTag
title: AtaPortReleaseQueueTag function
author: windows-driver-content
description: The AtaPortReleaseQueueTag routine releases the specified queue tag.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreleasequeuetag.htm
tech.root: storage
ms.assetid: 54399050-740f-4af8-ad85-cd3060f14af4
ms.date: 03/29/2018
ms.keywords: AtaPortReleaseQueueTag, AtaPortReleaseQueueTag routine [Storage Devices], atartns_cfdd9be6-53b5-4c4a-ac61-bc6a3cf48ea5.xml, irb/AtaPortReleaseQueueTag, storage.ataportreleasequeuetag
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
api_name:
-	AtaPortReleaseQueueTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReleaseQueueTag function


## -description


The <b>AtaPortReleaseQueueTag</b> routine releases the specified queue tag.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DeviceExtension

<p>A pointer to the channel extension.</p>


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number of the device.


### -param QueueTag [in]

Specifies the queue tag to be freed.


## -returns



None 




## -remarks



The miniport driver should call <b>AtaPortReleaseQueueTag</b> to free allocated queue tags by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550144">AtaPortAllocateQueueTag</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550144">AtaPortAllocateQueueTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550168">AtaPortInitializeQueueTag</a>
 

 

