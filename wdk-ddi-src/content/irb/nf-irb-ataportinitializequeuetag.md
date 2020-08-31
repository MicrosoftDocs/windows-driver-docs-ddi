---
UID: NF:irb.AtaPortInitializeQueueTag
title: AtaPortInitializeQueueTag function (irb.h)
description: The AtaPortInitializeQueueTag routine initializes the queue tag list for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportinitializequeuetag.htm
tech.root: storage
ms.assetid: f6d40f3e-4bc9-4b30-97ac-600a33280305
ms.date: 03/29/2018
keywords: ["AtaPortInitializeQueueTag function"]
ms.keywords: AtaPortInitializeQueueTag, AtaPortInitializeQueueTag routine [Storage Devices], atartns_2dd092e5-f635-4da7-8444-ffef8e5c75db.xml, irb/AtaPortInitializeQueueTag, storage.ataportinitializequeuetag
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
 - AtaPortInitializeQueueTag
 - irb/AtaPortInitializeQueueTag
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
 - AtaPortInitializeQueueTag
---

# AtaPortInitializeQueueTag function


## -description

The <b>AtaPortInitializeQueueTag</b> routine initializes the queue tag list for the specified device.
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

### -param MaxQueueTag 

[in]
Specifies the maximum allowed value for the queue tag.

## -returns

<b>AtaPortInitializeQueueTag</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>.

## -remarks

The miniport driver should call <b>AtaPortInitializeQueueTag</b> before it uses <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportallocatequeuetag">AtaPortAllocateQueueTag</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreleasequeuetag">AtaPortReleaseQueueTag</a> to allocate and release queue tags respectively. 

The values in the <i>TargetId</i> and <i>Lun</i> parameters specify the device to which the queue tag belongs. To generate channel specific queue tags, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportallocatequeuetag">AtaPortAllocateQueueTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreleasequeuetag">AtaPortReleaseQueueTag</a>

