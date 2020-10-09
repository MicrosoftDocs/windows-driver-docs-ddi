---
UID: NS:irb._IDE_CHANNEL_CONFIGURATION
title: _IDE_CHANNEL_CONFIGURATION (irb.h)
description: The IDE_CHANNEL_CONFIGURATION structure contains configuration information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_channel_configuration.htm
tech.root: storage
ms.assetid: 1ca9a198-ac6b-4837-9503-68eb7ca36527
ms.date: 03/29/2018
keywords: ["IDE_CHANNEL_CONFIGURATION structure"]
ms.keywords: "*PIDE_CHANNEL_CONFIGURATION, IDE_CHANNEL_CONFIGURATION, IDE_CHANNEL_CONFIGURATION structure [Storage Devices], PIDE_CHANNEL_CONFIGURATION, PIDE_CHANNEL_CONFIGURATION structure pointer [Storage Devices], _IDE_CHANNEL_CONFIGURATION, irb/IDE_CHANNEL_CONFIGURATION, irb/PIDE_CHANNEL_CONFIGURATION, storage.ide_channel_configuration, structs-ATA_79456267-9b2d-4f9a-beff-e44915bda026.xml"
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
targetos: Windows
req.typenames: IDE_CHANNEL_CONFIGURATION, *PIDE_CHANNEL_CONFIGURATION
f1_keywords:
 - _IDE_CHANNEL_CONFIGURATION
 - irb/_IDE_CHANNEL_CONFIGURATION
 - PIDE_CHANNEL_CONFIGURATION
 - irb/PIDE_CHANNEL_CONFIGURATION
 - IDE_CHANNEL_CONFIGURATION
 - irb/IDE_CHANNEL_CONFIGURATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - IDE_CHANNEL_CONFIGURATION
---

# _IDE_CHANNEL_CONFIGURATION structure


## -description

The IDE_CHANNEL_CONFIGURATION structure contains configuration information for the indicated channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields

### -field Version

The port driver sets this member to sizeof(IDE_CHANNEL_CONFIGURATION). The miniport driver should verify that the version is greater than or equal to the one it is using.

### -field ChannelNumber

The port driver sets this field to the number assigned for this channel. For non-native mode controllers, the primary channel will always be assigned 0 and the secondary channel will always be assigned 1.

### -field SupportedAdvances

####

### -field ChannelMode

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

### -field ChannelResources

The port driver uses this pointer to pass miniport hardware resources to be used to access the HBA on a PCI bus.

### -field NumberOfOverlappedRequests

The miniport driver should set this field to the number of requests the channel can handle at a time. By default, the port driver sets this to 1.

### -field MaxTargetId

The miniport should set this member to the maximum target ID supported on this channel. Typically, this is 1 less than the maximum number of devices supported on the channel. By default, the port driver sets this is set to 1 to indicate that 2 devices are supported on a channel.

### -field SyncWithIsr

Indicates support for unsynchronized I/O processing in the miniport driver. The miniport driver must set this member to <b>TRUE</b>.

### -field SupportsWmi

Indicates support for WMI. The miniport driver must set this member to <b>TRUE</b>.

### -field AdvancedChannelConfiguration