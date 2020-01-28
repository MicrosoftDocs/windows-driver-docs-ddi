---
UID: NS:irb._IDE_POWER_INFO
title: _IDE_POWER_INFO (irb.h)
description: The POWER_CHANGE_INFO structure is used in conjunction with the IDE_REQUEST_BLOCK to request a power state change.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\power_change_info.htm
tech.root: storage
ms.assetid: 10f6c449-f0f8-4261-825e-127c477c06eb
ms.date: 03/29/2018
ms.keywords: "*PIDE_POWER_INFO, IDE_POWER_INFO, IDE_POWER_INFO structure [Storage Devices], PIDE_POWER_INFO, PIDE_POWER_INFO structure pointer [Storage Devices], POWER_CHANGE_INFO, POWER_CHANGE_INFO structure [Storage Devices], _IDE_POWER_INFO, irb/IDE_POWER_INFO, irb/PIDE_POWER_INFO, storage.power_change_info, structs-ATA_b4b67f22-359b-4c12-ad21-7de1c39a8259.xml"
f1_keywords:
 - "irb/IDE_POWER_INFO"
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
- IDE_POWER_INFO
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_INFO, *PIDE_POWER_INFO
---

# _IDE_POWER_INFO structure


## -description


The POWER_CHANGE_INFO structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> to request a power state change.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field CurrentPowerState

Contains an enumeration value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ne-irb-ide_power_state">IDE_POWER_STATE</a> that indicates the current power state of the device.


### -field DesiredPowerState

Contains an enumeration value of type IDE_POWER_STATE that indicates the power state to which the device will be changed.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ne-irb-ide_power_state">IDE_POWER_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a>
 

 

