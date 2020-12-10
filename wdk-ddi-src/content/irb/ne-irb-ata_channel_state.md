---
UID: NE:irb.__unnamed_enum_4
title: ATA_CHANNEL_STATE (irb.h)
description: The ATA_CHANNEL_STATE enumeration type indicates the state of the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ata_channel_state.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ATA_CHANNEL_STATE enumeration"]
ms.keywords: ATA_CHANNEL_STATE, ATA_CHANNEL_STATE enumeration [Storage Devices], ChannelStateDisabled, ChannelStateEnabled, ChannelStateUnKnown, irb/ATA_CHANNEL_STATE, irb/ChannelStateDisabled, irb/ChannelStateEnabled, irb/ChannelStateUnKnown, storage.ata_channel_state, structs-ATA_317e3cc4-5b93-4942-9256-9418f692a8e2.xml
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
req.typenames: ATA_CHANNEL_STATE
f1_keywords:
 - ATA_CHANNEL_STATE
 - irb/ATA_CHANNEL_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - ATA_CHANNEL_STATE
---

# ATA_CHANNEL_STATE enumeration


## -description

The ATA_CHANNEL_STATE enumeration type indicates the state of the channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -enum-fields

### -field ChannelStateDisabled

Indicates that the channel is disabled.

### -field ChannelStateEnabled

Indicates that the channel is enabled.

### -field ChannelStateUnKnown

Indicates that the state of the channel is unknown.

## -remarks

The ATA_CHANNEL_STATE enumeration type is used in conjunction with the <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_enabled">AtaControllerChannelEnabled</a> routine to determine whether the channel is enabled.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_enabled">AtaControllerChannelEnabled</a>
