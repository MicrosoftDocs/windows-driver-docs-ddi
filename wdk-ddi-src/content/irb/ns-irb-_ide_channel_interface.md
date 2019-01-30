---
UID: NS:irb._IDE_CHANNEL_INTERFACE
title: _IDE_CHANNEL_INTERFACE (irb.h)
description: The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_channel_interface.htm
tech.root: storage
ms.assetid: 0a742dc2-fa1a-4b93-a136-52f4571bde22
ms.date: 03/29/2018
ms.keywords: "*PIDE_CHANNEL_INTERFACE, IDE_CHANNEL_INTERFACE, IDE_CHANNEL_INTERFACE structure [Storage Devices], PIDE_CHANNEL_INTERFACE, PIDE_CHANNEL_INTERFACE structure pointer [Storage Devices], _IDE_CHANNEL_INTERFACE, irb/IDE_CHANNEL_INTERFACE, irb/PIDE_CHANNEL_INTERFACE, storage.ide_channel_interface, structs-ATA_8641c5e5-fe37-4576-a500-1f6a2cdbb23b.xml"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	IDE_CHANNEL_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: IDE_CHANNEL_INTERFACE, *PIDE_CHANNEL_INTERFACE
---

# _IDE_CHANNEL_INTERFACE structure


## -description


The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Version

The port driver sets this member to sizeof(IDE_CHANNEL_INTERFACE). The miniport driver should verify that the version is greater than or equal to the one it is using.


### -field ChannelNumber

The port driver sets this field to the number assigned for this channel. For non-native mode controllers, the primary channel will always be assigned 0 and the secondary channel will always be assigned 1.


### -field Reserved

Reserved for future use. The miniport driver must not use this field.


### -field ReservedUlong



#### 


### -field IdeHwInitialize


### -field IdeHwBuildIo


### -field IdeHwStartIo


### -field IdeHwInterrupt


### -field IdeHwReset


### -field IdeHwControl


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557462">IdeHwBuildIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557467">IdeHwInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558992">IdeHwInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558998">IdeHwReset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559003">IdeHwStartIo</a>
 

 

