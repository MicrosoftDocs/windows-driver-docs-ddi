---
UID: NC:irb.IDE_TRANSFER_MODE_SELECT
title: IDE_TRANSFER_MODE_SELECT (irb.h)
description: The AtaControllerTransferModeSelect miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\atacontrollertransfermodeselect.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["IDE_TRANSFER_MODE_SELECT callback function"]
ms.keywords: AtaControllerTransferModeSelect, AtaControllerTransferModeSelect routine [Storage Devices], IDE_TRANSFER_MODE_SELECT, atartns_c4d206b0-4a6a-49ce-b729-97c8b01e4089.xml, irb/AtaControllerTransferModeSelect, storage.atacontrollertransfermodeselect
req.header: irb.h
req.include-header: Irb.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDE_TRANSFER_MODE_SELECT
 - irb/IDE_TRANSFER_MODE_SELECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - irb.h
api_name:
 - IDE_TRANSFER_MODE_SELECT
---

# IDE_TRANSFER_MODE_SELECT callback function

## -description

The **AtaControllerTransferModeSelect** miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -parameters

### -param ControllerExtension

[in] A pointer to the controller extension.

### -param TransferModeSelect

[in, out] A pointer to a structure of type [**IDE_TRANSFER_MODE_PARAMETERS**](ns-irb-_ide_transfer_mode_parameters.md) that indicates to the miniport driver the channel on which to set the transfer modes and which transfer modes are available.

## -returns

**AtaControllerTransferModeSelect** returns TRUE to acknowledge the receipt of the transfer mode parameters. The miniport driver ignores a return value of FALSE.

## -remarks

The **AtaControllerTransferModeSelect** miniport driver routine must select the appropriate timing modes and program the controller for the selected modes. The miniport driver must select at least one programmed input/output (PIO) mode for the indicated channel, and preferably at least one direct memory access (DMA) timing mode also. To communicate to the caller the transfer modes that it selected, the miniport driver sets the appropriate bits in the **TransferModeSelected** member of the IDE_TRANSFER_MODE_PARAMETERS structure.

**AtaControllerTransferModeSelect** is an optional routine.

## -see-also

[**IDE_TRANSFER_MODE_PARAMETERS**](ns-irb-_ide_transfer_mode_parameters.md)
