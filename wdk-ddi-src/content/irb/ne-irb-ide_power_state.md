---
UID: NE:irb.__unnamed_enum_3
title: IDE_POWER_STATE (irb.h)
description: The IDE_POWER_STATE enumeration type indicates that power state of the device.
old-location: storage\ide_power_state.htm
tech.root: storage
ms.assetid: b54655ac-b7ac-4026-9d9d-75dd139ac059
ms.date: 03/29/2018
keywords: ["IDE_POWER_STATE enumeration"]
ms.keywords: IDE_POWER_STATE, IDE_POWER_STATE enumeration [Storage Devices], IdePowerD0, IdePowerD3, IdePowerUnSpecified, irb/IDE_POWER_STATE, irb/IdePowerD0, irb/IdePowerD3, irb/IdePowerUnSpecified, storage.ide_power_state, structs-ATA_82594916-763d-46c4-9a40-e1e4f0c32e13.xml
f1_keywords:
 - "irb/IDE_POWER_STATE"
 - "IDE_POWER_STATE"
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
- IDE_POWER_STATE
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# IDE_POWER_STATE enumeration


## -description


The IDE_POWER_STATE enumeration type indicates that power state of the device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -enum-fields




### -field IdePowerUnSpecified

Indicates that the power level is unspecified.


### -field IdePowerD0

Indicates a device power level of 0.


### -field IdePowerD3

Indicates a device power level of 3.


## -remarks



The IDE_POWER_STATE enumeration type is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportrequestpowerstatechange">AtaPortRequestPowerStateChange</a> routine to request a power state transition for a device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportrequestpowerstatechange">AtaPortRequestPowerStateChange</a>
 

 

