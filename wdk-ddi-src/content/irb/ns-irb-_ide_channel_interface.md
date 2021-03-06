---
UID: NS:irb._IDE_CHANNEL_INTERFACE
title: IDE_CHANNEL_INTERFACE (irb.h)
description: The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_channel_interface.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IDE_CHANNEL_INTERFACE structure"]
ms.keywords: "*PIDE_CHANNEL_INTERFACE, IDE_CHANNEL_INTERFACE, IDE_CHANNEL_INTERFACE structure [Storage Devices], PIDE_CHANNEL_INTERFACE, PIDE_CHANNEL_INTERFACE structure pointer [Storage Devices], _IDE_CHANNEL_INTERFACE, irb/IDE_CHANNEL_INTERFACE, irb/PIDE_CHANNEL_INTERFACE, storage.ide_channel_interface, structs-ATA_8641c5e5-fe37-4576-a500-1f6a2cdbb23b.xml"
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
req.typenames: IDE_CHANNEL_INTERFACE, *PIDE_CHANNEL_INTERFACE
f1_keywords:
 - _IDE_CHANNEL_INTERFACE
 - irb/_IDE_CHANNEL_INTERFACE
 - PIDE_CHANNEL_INTERFACE
 - irb/PIDE_CHANNEL_INTERFACE
 - IDE_CHANNEL_INTERFACE
 - irb/IDE_CHANNEL_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - _IDE_CHANNEL_INTERFACE
 - PIDE_CHANNEL_INTERFACE
 - IDE_CHANNEL_INTERFACE
---

# IDE_CHANNEL_INTERFACE structure

## -description

The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -struct-fields

### -field Version

The port driver sets this member to sizeof(IDE_CHANNEL_INTERFACE). The miniport driver should verify that the version is greater than or equal to the one it is using.

### -field ChannelNumber

The port driver sets this field to the number assigned for this channel. For non-native mode controllers, the primary channel will always be assigned 0 and the secondary channel will always be assigned 1.

### -field Reserved

Reserved. The miniport driver must not use this field.

### -field ReservedUlong

Reserved. The miniport driver must not use this field.

### -field IdeHwInitialize

The miniport's [**IdeHwInitialize**](nc-irb-ide_hw_initialize.md) routine.

### -field IdeHwBuildIo

The miniport's [**IdeHwBuildIo**](nc-irb-ide_hw_buildio.md) routine.

### -field IdeHwStartIo

The miniport's [**IdeHwStartIo**](nc-irb-ide_hw_startio.md) routine.

### -field IdeHwInterrupt

The miniport's [**IdeHwInterrupt**](nc-irb-ide_hw_interrupt.md) routine.

### -field IdeHwReset

The miniport's [**IdeHwReset**](nc-irb-ide_hw_reset.md) routine.

### -field IdeHwControl

The miniport's [**IdeHwControl**](nc-irb-ide_hw_control.md) routine.

## -see-also

[**IdeHwBuildIo**](nc-irb-ide_hw_buildio.md)

[**IdeHwControl**](nc-irb-ide_hw_control.md)

[**IdeHwInitialize**](nc-irb-ide_hw_initialize.md)

[**IdeHwInterrupt**](nc-irb-ide_hw_interrupt.md)

[**IdeHwReset**](nc-irb-ide_hw_reset.md)

[**IdeHwStartIo**](nc-irb-ide_hw_startio.md)
