---
UID: NF:irb.AtaPortAllocateQueueTag
title: AtaPortAllocateQueueTag function
author: windows-driver-content
description: The AtaPortAllocateQueueTag routine returns a queue tag for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportallocatequeuetag.htm
old-project: storage
ms.assetid: e298f51b-58b7-4f04-85d3-3ee809deb489
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, AtaPortAllocateQueueTag, AtaPortAllocateQueueTag routine [Storage Devices], P, Q, T, a, atartns_bae1e6d8-6ae5-4428-88a6-334a63fcefae.xml, c, e, g, irb/AtaPortAllocateQueueTag, l, o, r, storage.ataportallocatequeuetag, t, u"
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	AtaPortAllocateQueueTag
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortAllocateQueueTag function


## -description


The <b>AtaPortAllocateQueueTag</b> routine returns a queue tag for the specified device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
UCHAR AtaPortAllocateQueueTag(
  _In_ PVOID ChannelExtension,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun
);
````


## -parameters




### -param DeviceExtension

TBD


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number (LUN) of the device.


#### - ChannelExtension [in]

A pointer to the channel extension.


## -returns



<b>AtaPortAllocateQueueTag</b> returns a valid queue tag if one can be allocated. A value of 0 is returned if a queue tag could not be allocated. 




## -remarks



The <b>AtaPortAllocateQueueTag</b> routine allocates either a per device queue tag or a per channel queue tag. To generate a per channel queue tag, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED. 




## -see-also

<a href="..\irb\nf-irb-ataportinitializequeuetag.md">AtaPortInitializeQueueTag</a>



<a href="..\irb\nf-irb-ataportreleasequeuetag.md">AtaPortReleaseQueueTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortAllocateQueueTag routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

