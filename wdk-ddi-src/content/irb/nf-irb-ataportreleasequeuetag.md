---
UID: NF:irb.AtaPortReleaseQueueTag
title: AtaPortReleaseQueueTag function (irb.h)
description: The AtaPortReleaseQueueTag routine releases the specified queue tag.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreleasequeuetag.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortReleaseQueueTag function"]
ms.keywords: AtaPortReleaseQueueTag, AtaPortReleaseQueueTag routine [Storage Devices], atartns_cfdd9be6-53b5-4c4a-ac61-bc6a3cf48ea5.xml, irb/AtaPortReleaseQueueTag, storage.ataportreleasequeuetag
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
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortReleaseQueueTag
 - irb/AtaPortReleaseQueueTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ataport.lib
 - ataport.dll
 - pciidex.lib
 - pciidex.dll
api_name:
 - AtaPortReleaseQueueTag
---

# AtaPortReleaseQueueTag function


## -description

The <b>AtaPortReleaseQueueTag</b> routine releases the specified queue tag.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param DeviceExtension

<p>A pointer to the channel extension.</p>

### -param TargetId 

[in]
Specifies the target identifier of the device.

### -param Lun 

[in]
Specifies the logical unit number of the device.

### -param QueueTag 

[in]
Specifies the queue tag to be freed.

## -remarks

The miniport driver should call <b>AtaPortReleaseQueueTag</b> to free allocated queue tags by using <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportallocatequeuetag">AtaPortAllocateQueueTag</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportallocatequeuetag">AtaPortAllocateQueueTag</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializequeuetag">AtaPortInitializeQueueTag</a>
