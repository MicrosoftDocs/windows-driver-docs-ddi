---
UID: NC:irb.IDE_TRANSFER_MODE_SELECT
title: IDE_TRANSFER_MODE_SELECT (irb.h)
description: The AtaControllerTransferModeSelect miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\atacontrollertransfermodeselect.htm
tech.root: storage
ms.assetid: 3ee46b54-791f-4eac-84d7-5a0093b6984a
ms.date: 03/29/2018
ms.keywords: AtaControllerTransferModeSelect, AtaControllerTransferModeSelect routine [Storage Devices], IDE_TRANSFER_MODE_SELECT, atartns_c4d206b0-4a6a-49ce-b729-97c8b01e4089.xml, irb/AtaControllerTransferModeSelect, storage.atacontrollertransfermodeselect
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	irb.h
api_name:
-	AtaControllerTransferModeSelect
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDE_TRANSFER_MODE_SELECT callback function


## -description


The <b><i>AtaControllerTransferModeSelect</i></b> miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ControllerExtension [in]

A pointer to the controller extension.


### -param TransferModeSelect








#### - TransferModeParams [in, out]

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559151">IDE_TRANSFER_MODE_PARAMETERS</a> that indicates to the miniport driver the channel on which to set the transfer modes and which transfer modes are available. 


## -returns



<b><i>AtaControllerTransferModeSelect</i></b> returns <b>TRUE</b> to acknowledge the receipt of the transfer mode parameters. The miniport driver ignores a return value of <b>FALSE</b>.




## -remarks



The <b><i>AtaControllerTransferModeSelect</i></b> miniport driver routine must select the appropriate timing modes and program the controller for the selected modes. The miniport driver must select at least one programmed input/output (PIO) mode for the indicated channel, and preferably at least one direct memory access (DMA) timing mode also. To communicate to the caller the transfer modes that it selected, the miniport driver sets the appropriate bits in the <b>TransferModeSelected</b> member of the IDE_TRANSFER_MODE_PARAMETERS structure.

<b><i>AtaControllerTransferModeSelect</i></b> is an optional routine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559151">IDE_TRANSFER_MODE_PARAMETERS</a>
 

 

