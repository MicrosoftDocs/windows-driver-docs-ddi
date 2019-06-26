---
UID: NS:irb._IDE_TRANSFER_MODE_PARAMETERS
title: _IDE_TRANSFER_MODE_PARAMETERS (irb.h)
description: The IDE_TRANSFER_MODE_PARAMETERS structure is used in conjunction with the miniport driver's AtaControllerTransferModeSelect routine to set the transfer mode parameters on a channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ide_transfer_mode_parameters.htm
tech.root: storage
ms.assetid: 66e6efd0-6651-4c87-94ba-d9d3b9191339
ms.date: 03/29/2018
ms.keywords: "*PIDE_TRANSFER_MODE_PARAMETERS, IDE_TRANSFER_MODE_PARAMETERS, IDE_TRANSFER_MODE_PARAMETERS structure [Storage Devices], PIDE_TRANSFER_MODE_PARAMETERS, PIDE_TRANSFER_MODE_PARAMETERS structure pointer [Storage Devices], _IDE_TRANSFER_MODE_PARAMETERS, irb/IDE_TRANSFER_MODE_PARAMETERS, irb/PIDE_TRANSFER_MODE_PARAMETERS, storage.ide_transfer_mode_parameters, structs-ATA_41b44f2c-8685-45fe-8c56-2a9a648782b4.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- irb.h
api_name:
- IDE_TRANSFER_MODE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: IDE_TRANSFER_MODE_PARAMETERS, *PIDE_TRANSFER_MODE_PARAMETERS
---

# _IDE_TRANSFER_MODE_PARAMETERS structure


## -description


The IDE_TRANSFER_MODE_PARAMETERS structure is used in conjunction with the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_transfer_mode_select">AtaControllerTransferModeSelect</a> routine to set the transfer mode parameters on a channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field ChannelNumber

Indicates the channel number whose mode parameters are to be set.


### -field DeviceType

Contains an enumeration value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ne-irb-ide_device_type">IDE_DEVICE_TYPE</a> that indicates the type of device. The miniport driver should not select a transfer mode if the device type is <b>DeviceNotExist</b>.


### -field IoReadySupported

Indicates when <b>TRUE</b> that bit 11 of word 49 of the indicated device's identify data is set to 1. An IDE request with a function value of IRB_FUNCTION_ATA_IDENTIFY will retrieve a device's identify data. For more information about ATA identify data, see the sections on the Identify Device information packet in version 6.0 of the <i>ATA/ATAPI specification</i>.


### -field DeviceTransferModeSupported

Contains a bitmap that indicates the supported transfer modes for each of the devices on the channel. The port driver sets this member. The miniport driver must not select a transfer mode that the port driver does not support. For more information about this member, see the <b>Remarks</b> section.


### -field DeviceTransferModeCurrent

Contains a bitmap that indicates the current transfer mode settings for each of the device on the channel. The port driver retrieves the current transfer mode of the devices from their identify device data. For more information about this member, see the <b>Remarks</b> section.


### -field DeviceTransferModeSelected

Contains a bitmap that indicates the selected transfer mode settings for each of the device on the channel. The miniport driver should use this member to indicate to the port driver which transfer modes it selects. For more information about this member, see the <b>Remarks</b> section.


## -remarks



Member arrays <b>DeviceTransferModeSupported</b>, <b>DeviceTransferModeCurrent</b>, and <b>DeviceTransferModeSelected</b> are arrays of ULONG bitmaps indicating combinations of PIO and DMA transfer modes. The bitmaps are defined as follows:

// PIO Modes

#define PIO_MODE0           (1 << 0)

#define PIO_MODE1           (1 << 1)

#define PIO_MODE2           (1 << 2)

#define PIO_MODE3           (1 << 3)

#define PIO_MODE4           (1 << 4)

// Single-word DMA Modes

#define SWDMA_MODE0         (1 << 5)

#define SWDMA_MODE1         (1 << 6)

#define SWDMA_MODE2         (1 << 7)

// Multi-word DMA Modes

#define MWDMA_MODE0         (1 << 8)

#define MWDMA_MODE1         (1 << 9)

#define MWDMA_MODE2         (1 << 10)

// Ultra DMA Modes

#define UDMA_MODE0          (1 << 11)

#define UDMA_MODE1          (1 << 12)

#define UDMA_MODE2          (1 << 13)

#define UDMA_MODE3          (1 << 14)

#define UDMA_MODE4          (1 << 15)

#define UDMA_MODE5          (1 << 16)




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_transfer_mode_select">AtaControllerTransferModeSelect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ne-irb-ide_device_type">IDE_DEVICE_TYPE</a>
 

 

