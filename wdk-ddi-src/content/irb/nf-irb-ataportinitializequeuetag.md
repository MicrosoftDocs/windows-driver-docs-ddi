---
UID: NF:irb.AtaPortInitializeQueueTag
title: AtaPortInitializeQueueTag function
author: windows-driver-content
description: The AtaPortInitializeQueueTag routine initializes the queue tag list for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportinitializequeuetag.htm
old-project: storage
ms.assetid: f6d40f3e-4bc9-4b30-97ac-600a33280305
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortInitializeQueueTag, AtaPortInitializeQueueTag routine [Storage Devices], atartns_2dd092e5-f635-4da7-8444-ffef8e5c75db.xml, irb/AtaPortInitializeQueueTag, storage.ataportinitializequeuetag
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	AtaPortInitializeQueueTag
product: Windows
targetos: Windows
req.typenames: 
---

# AtaPortInitializeQueueTag function


## -description


The <b>AtaPortInitializeQueueTag</b> routine initializes the queue tag list for the specified device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DeviceExtension

TBD


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number (LUN) of the device.


### -param MaxQueueTag [in]

Specifies the maximum allowed value for the queue tag.


#### - ChannelExtension [in]

A pointer to the channel extension.


## -returns



<b>AtaPortInitializeQueueTag</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. 




## -remarks



The miniport driver should call <b>AtaPortInitializeQueueTag</b> before it uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff550144">AtaPortAllocateQueueTag</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550214">AtaPortReleaseQueueTag</a> to allocate and release queue tags respectively. 

The values in the <i>TargetId</i> and <i>Lun</i> parameters specify the device to which the queue tag belongs. To generate channel specific queue tags, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550144">AtaPortAllocateQueueTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550214">AtaPortReleaseQueueTag</a>
 

 

