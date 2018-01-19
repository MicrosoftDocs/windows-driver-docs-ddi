---
UID: NF:irb.AtaPortInitializeQueueTag
title: AtaPortInitializeQueueTag function
author: windows-driver-content
description: The AtaPortInitializeQueueTag routine initializes the queue tag list for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportinitializequeuetag.htm
old-project: storage
ms.assetid: f6d40f3e-4bc9-4b30-97ac-600a33280305
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortInitializeQueueTag
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
req.alt-api: AtaPortInitializeQueueTag
req.alt-loc: ataport.lib,ataport.dll,pciidex.lib,pciidex.dll
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
req.typenames: IDE_POWER_STATE
---

# AtaPortInitializeQueueTag function



## -description
The <b>AtaPortInitializeQueueTag</b> routine initializes the queue tag list for the specified device.



## -syntax

````
BOOLEAN AtaPortInitializeQueueTag(
  _In_ PVOID ChannelExtension,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ UCHAR MaxQueueTag
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension.


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number (LUN) of the device.


### -param MaxQueueTag [in]

Specifies the maximum allowed value for the queue tag.


## -returns
<b>AtaPortInitializeQueueTag</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. 


## -remarks
The miniport driver should call <b>AtaPortInitializeQueueTag</b> before it uses <a href="..\irb\nf-irb-ataportallocatequeuetag.md">AtaPortAllocateQueueTag</a> and <a href="..\irb\nf-irb-ataportreleasequeuetag.md">AtaPortReleaseQueueTag</a> to allocate and release queue tags respectively. 

The values in the <i>TargetId</i> and <i>Lun</i> parameters specify the device to which the queue tag belongs. To generate channel specific queue tags, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED. 


## -see-also
<dl>
<dt>
<a href="..\irb\nf-irb-ataportallocatequeuetag.md">AtaPortAllocateQueueTag</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportreleasequeuetag.md">AtaPortReleaseQueueTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortInitializeQueueTag routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

