---
UID: NF:irb.AtaPortAllocateQueueTag
title: AtaPortAllocateQueueTag function (irb.h)
description: The AtaPortAllocateQueueTag routine returns a queue tag for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportallocatequeuetag.htm
tech.root: storage
ms.assetid: e298f51b-58b7-4f04-85d3-3ee809deb489
ms.date: 03/29/2018
keywords: ["AtaPortAllocateQueueTag function"]
ms.keywords: AtaPortAllocateQueueTag, AtaPortAllocateQueueTag routine [Storage Devices], atartns_bae1e6d8-6ae5-4428-88a6-334a63fcefae.xml, irb/AtaPortAllocateQueueTag, storage.ataportallocatequeuetag
f1_keywords:
 - "irb/AtaPortAllocateQueueTag"
 - "AtaPortAllocateQueueTag"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- irb.h
api_name:
- AtaPortAllocateQueueTag
targetos: Windows
req.typenames: 
---

# AtaPortAllocateQueueTag function


## -description


The <b>AtaPortAllocateQueueTag</b> routine returns a queue tag for the specified device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DeviceExtension

<p>A pointer to the channel extension.</p>


### -param TargetId 
[in]
Specifies the target identifier of the device.


### -param Lun 
[in]
Specifies the logical unit number (LUN) of the device.


## -returns



<b>AtaPortAllocateQueueTag</b> returns a valid queue tag if one can be allocated. A value of 0 is returned if a queue tag could not be allocated. 




## -remarks



The <b>AtaPortAllocateQueueTag</b> routine allocates either a per device queue tag or a per channel queue tag. To generate a per channel queue tag, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportinitializequeuetag">AtaPortInitializeQueueTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreleasequeuetag">AtaPortReleaseQueueTag</a>
 

 

