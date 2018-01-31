---
UID: NS:irb._IDE_CHANNEL_CONFIGURATION
title: "_IDE_CHANNEL_CONFIGURATION"
author: windows-driver-content
description: The IDE_CHANNEL_CONFIGURATION structure contains configuration information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_channel_configuration.htm
old-project: storage
ms.assetid: 1ca9a198-ac6b-4837-9503-68eb7ca36527
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: irb/PIDE_CHANNEL_CONFIGURATION, IDE_CHANNEL_CONFIGURATION, _IDE_CHANNEL_CONFIGURATION, PIDE_CHANNEL_CONFIGURATION structure pointer [Storage Devices], structs-ATA_79456267-9b2d-4f9a-beff-e44915bda026.xml, storage.ide_channel_configuration, PIDE_CHANNEL_CONFIGURATION, irb/IDE_CHANNEL_CONFIGURATION, IDE_CHANNEL_CONFIGURATION structure [Storage Devices], *PIDE_CHANNEL_CONFIGURATION
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
-	IDE_CHANNEL_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: "*PIDE_CHANNEL_CONFIGURATION, IDE_CHANNEL_CONFIGURATION"
---

# _IDE_CHANNEL_CONFIGURATION structure


## -description


The IDE_CHANNEL_CONFIGURATION structure contains configuration information for the indicated channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_CHANNEL_CONFIGURATION {
  USHORT                              Version;
  UCHAR                               ChannelNumber;
  SUPPORTED_ADVANCES                  SupportedAdvances;
  IDE_OPERATION_MODE                  ChannelMode;
  PIDE_MINIPORT_RESOURCES             ChannelResources;
  UCHAR                               NumberOfOverlappedRequests;
  UCHAR                               MaxTargetId;
  BOOLEAN                             SyncWithIsr;
  BOOLEAN                             SupportsWmi;
  PIDE_ADVANCED_CHANNEL_CONFIGURATION AdvancedChannelConfiguration;
} IDE_CHANNEL_CONFIGURATION, *PIDE_CHANNEL_CONFIGURATION;
````


## -struct-fields




#### - Version

The port driver sets this member to sizeof(IDE_CHANNEL_CONFIGURATION). The miniport driver should verify that the version is greater than or equal to the one it is using.


#### - ChannelNumber

The port driver sets this field to the number assigned for this channel. For non-native mode controllers, the primary channel will always be assigned 0 and the secondary channel will always be assigned 1.


#### - SupportedAdvances



#### 



#### - ChannelMode

The port driver sets this field to inform the ATA miniport which mode it is running at. There are three possible modes:
<table>
<tr>
<th>Mode</th>
<th>Description</th>
</tr>
<tr>
<td>
IdeModeNormal 

</td>
<td>
This is the standard full capabilities mode where the ATA miniport may operate normally.

</td>
</tr>
<tr>
<td>
IdeModeDump,

</td>
<td>
This is the limited no memory mode that an ATA miniport operates in during hibernate or crashdump. Call Back Routines and Registry Access Routines cannot be used when in this mode.

</td>
</tr>
<tr>
<td>
IdeModeRemovableBay

</td>
<td>
Similar to the IdeModeNormal, this indicates the ATA miniport must take extra steps to enable enumeration of devices that may have just been hotplugged onto a Parallel ATA bus.

</td>
</tr>
</table> 


#### - ChannelResources

The port driver uses this pointer to pass miniport hardware resources to be used to access the HBA on a PCI bus.


#### - NumberOfOverlappedRequests

The miniport driver should set this field to the number of requests the channel can handle at a time. By default, the port driver sets this to 1.


#### - MaxTargetId

The miniport should set this member to the maximum target ID supported on this channel. Typically, this is 1 less than the maximum number of devices supported on the channel. By default, the port driver sets this is set to 1 to indicate that 2 devices are supported on a channel.


#### - SyncWithIsr

Indicates support for unsynchronized I/O processing in the miniport driver. The miniport driver must set this member to <b>TRUE</b>.


#### - SupportsWmi

Indicates support for WMI. The miniport driver must set this member to <b>TRUE</b>.


#### - AdvancedChannelConfiguration


