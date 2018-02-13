---
UID: NC:irb.IDE_TRANSFER_MODE_SELECT
title: IDE_TRANSFER_MODE_SELECT
author: windows-driver-content
description: The AtaControllerTransferModeSelect miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\atacontrollertransfermodeselect.htm
old-project: storage
ms.assetid: 3ee46b54-791f-4eac-84d7-5a0093b6984a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.atacontrollertransfermodeselect, AtaControllerTransferModeSelect routine [Storage Devices], AtaControllerTransferModeSelect, IDE_TRANSFER_MODE_SELECT, IDE_TRANSFER_MODE_SELECT, irb/AtaControllerTransferModeSelect, atartns_c4d206b0-4a6a-49ce-b729-97c8b01e4089.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	irb.h
apiname:
-	AtaControllerTransferModeSelect
product: Windows
targetos: Windows
req.typenames: LUID
---

# IDE_TRANSFER_MODE_SELECT callback


## -description


The <b><i>AtaControllerTransferModeSelect</i></b> miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -prototype


````
IDE_TRANSFER_MODE_SELECT AtaControllerTransferModeSelect;

BOOLEAN AtaControllerTransferModeSelect(
  _In_    PVOID                         ControllerExtension,
  _Inout_ PIDE_TRANSFER_MODE_PARAMETERS TransferModeParams
)
{ ... }
````


## -parameters




### -param ControllerExtension [in]

A pointer to the controller extension.


### -param TransferModeSelect








#### - TransferModeParams [in, out]

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_transfer_mode_parameters.md">IDE_TRANSFER_MODE_PARAMETERS</a> that indicates to the miniport driver the channel on which to set the transfer modes and which transfer modes are available. 


## -returns



<b><i>AtaControllerTransferModeSelect</i></b> returns <b>TRUE</b> to acknowledge the receipt of the transfer mode parameters. The miniport driver ignores a return value of <b>FALSE</b>.




## -remarks



The <b><i>AtaControllerTransferModeSelect</i></b> miniport driver routine must select the appropriate timing modes and program the controller for the selected modes. The miniport driver must select at least one programmed input/output (PIO) mode for the indicated channel, and preferably at least one direct memory access (DMA) timing mode also. To communicate to the caller the transfer modes that it selected, the miniport driver sets the appropriate bits in the <b>TransferModeSelected</b> member of the IDE_TRANSFER_MODE_PARAMETERS structure.

<b><i>AtaControllerTransferModeSelect</i></b> is an optional routine. 




## -see-also

<a href="..\irb\ns-irb-_ide_transfer_mode_parameters.md">IDE_TRANSFER_MODE_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaControllerTransferModeSelect routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

