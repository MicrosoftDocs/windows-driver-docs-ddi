---
UID: NS:irb._IDE_CHANNEL_INTERFACE
title: "_IDE_CHANNEL_INTERFACE"
author: windows-driver-content
description: The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_channel_interface.htm
old-project: storage
ms.assetid: 0a742dc2-fa1a-4b93-a136-52f4571bde22
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: irb/IDE_CHANNEL_INTERFACE, IDE_CHANNEL_INTERFACE structure [Storage Devices], storage.ide_channel_interface, IDE_CHANNEL_INTERFACE, irb/PIDE_CHANNEL_INTERFACE, PIDE_CHANNEL_INTERFACE structure pointer [Storage Devices], structs-ATA_8641c5e5-fe37-4576-a500-1f6a2cdbb23b.xml, PIDE_CHANNEL_INTERFACE, *PIDE_CHANNEL_INTERFACE, _IDE_CHANNEL_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	IDE_CHANNEL_INTERFACE
product: Windows
targetos: Windows
req.typenames: IDE_CHANNEL_INTERFACE, *PIDE_CHANNEL_INTERFACE
---

# _IDE_CHANNEL_INTERFACE structure


## -description


The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_CHANNEL_INTERFACE {
  USHORT            Version;
  UCHAR             ChannelNumber;
  UCHAR             Reserved;
  ULONG             ReservedUlong;
  IDE_HW_INITIALIZE IdeHwInitialize;
  IDE_HW_BUILDIO    IdeHwBuildIo;
  IDE_HW_STARTIO    IdeHwStartIo;
  IDE_HW_INTERRUPT  IdeHwInterrupt;
  IDE_HW_RESET      IdeHwReset;
  IDE_HW_CONTROL    IdeHwControl;
} IDE_CHANNEL_INTERFACE, *PIDE_CHANNEL_INTERFACE;
````


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559003">IdeHwStartIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558992">IdeHwInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557467">IdeHwInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558998">IdeHwReset</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_CHANNEL_INTERFACE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

