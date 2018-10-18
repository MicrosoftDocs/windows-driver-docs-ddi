---
UID: NS:irb._IDE_CONTROLLER_INTERFACE
title: "_IDE_CONTROLLER_INTERFACE"
author: windows-driver-content
description: The IDE_CONTROLLER_INTERFACE structure is used to pass controller configuration information between the port driver and the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_controller_interface.htm
tech.root: storage
ms.assetid: cb18f7d9-f9e8-436d-8d61-3641730bd8a2
ms.date: 3/29/2018
ms.keywords: "*PIDE_CONTROLLER_INTERFACE, IDE_CONTROLLER_INTERFACE, IDE_CONTROLLER_INTERFACE structure [Storage Devices], PIDE_CONTROLLER_INTERFACE, PIDE_CONTROLLER_INTERFACE structure pointer [Storage Devices], _IDE_CONTROLLER_INTERFACE, irb/IDE_CONTROLLER_INTERFACE, irb/PIDE_CONTROLLER_INTERFACE, storage.ide_controller_interface, structs-ATA_3b2abcb7-676c-44c9-a2a3-c4efb0f1e032.xml"
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
-	IDE_CONTROLLER_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: IDE_CONTROLLER_INTERFACE, *PIDE_CONTROLLER_INTERFACE
---

# _IDE_CONTROLLER_INTERFACE structure


## -description


The IDE_CONTROLLER_INTERFACE structure is used to pass controller configuration information between the port driver and the miniport driver.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Version

The port driver sets this field to indicate the version of the port driver. The port driver sets the version to sizeof(IDE_CONTROLLER_INTERFACE). The miniport driver should verify that the version is greater than or equal to the one it is using.


### -field Reserved

Reserved for future use. The miniport driver shall not use this field.


### -field ControllerExtensionSize

Specifies the size in bytes required by a miniport driver for its controller device extension.


### -field ChannelExtensionSize

Specifies the size in bytes required by a miniport driver for its per-channel device extension.


### -field AlignmentMask

Contains a mask indicating the alignment restrictions for buffers required by the HBA for transfer operations. Valid mask values are also restricted by characteristics of the memory managers on different versions of Windows. Under Windows 2000 and Windows XP, the valid mask values are 0 (byte-aligned), 1 (word-aligned), 3 (DWORD-aligned) and 7 (double DWORD-aligned). The miniport driver should set this mask if the HBA supports scatter/gather.


### -field AtaChannelInitRoutine

Pointer to the miniport's <b>AtaChannelInitRoutine</b> routine. The miniport needs to set this entry point only if it supports the Channel Interface.


### -field AtaControllerChannelEnabled

Pointer to the miniport's <b>AtaControllerChannelEnabled</b> routine. This is an optional entry point.


### -field AtaControllerTransferModeSelect

Pointer to the miniport's <b>AtaControllerTransferModeSelect</b> routine. This is an optional entry point.


### -field AtaAdapterControl

Pointer to the miniport's <b>AtaControllerAdapterControl</b> routine. This is a required entry point.

