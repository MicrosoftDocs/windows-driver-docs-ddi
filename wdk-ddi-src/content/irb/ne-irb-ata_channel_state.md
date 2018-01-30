---
UID: NE:irb.ATA_CHANNEL_STATE
title: ATA_CHANNEL_STATE
author: windows-driver-content
description: The ATA_CHANNEL_STATE enumeration type indicates the state of the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ata_channel_state.htm
old-project: storage
ms.assetid: 97df2db8-6a42-46d4-bc31-babb124635ee
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ATA_CHANNEL_STATE enumeration [Storage Devices], irb/ChannelStateUnKnown, ATA_CHANNEL_STATE, storage.ata_channel_state, ChannelStateEnabled, structs-ATA_317e3cc4-5b93-4942-9256-9418f692a8e2.xml, irb/ChannelStateDisabled, irb/ATA_CHANNEL_STATE, ChannelStateUnKnown, ChannelStateDisabled, irb/ChannelStateEnabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	ATA_CHANNEL_STATE
product: Windows
targetos: Windows
req.typenames: ATA_CHANNEL_STATE
---

# ATA_CHANNEL_STATE enumeration


## -description


The ATA_CHANNEL_STATE enumeration type indicates the state of the channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef enum  { 
  ChannelStateDisabled  = 0,
  ChannelStateEnabled   = 1,
  ChannelStateUnKnown   = 2
} ATA_CHANNEL_STATE;
````


## -enum-fields




### -field ChannelStateDisabled

Indicates that the channel is disabled.


### -field ChannelStateEnabled

Indicates that the channel is enabled.


### -field ChannelStateUnKnown

Indicates that the state of the channel is unknown.


## -remarks


The ATA_CHANNEL_STATE enumeration type is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a> routine to determine whether the channel is enabled.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550142">AtaControllerChannelEnabled</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ATA_CHANNEL_STATE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

