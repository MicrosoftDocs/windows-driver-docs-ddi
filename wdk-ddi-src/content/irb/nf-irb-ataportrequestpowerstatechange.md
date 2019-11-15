---
UID: NF:irb.AtaPortRequestPowerStateChange
title: AtaPortRequestPowerStateChange function (irb.h)
description: The AtaPortRequestPowerStateChange routine requests a power state transition for the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestpowerstatechange.htm
tech.root: storage
ms.assetid: 37cf1552-2cbe-4b80-b220-cfa853674e1b
ms.date: 03/29/2018
ms.keywords: AtaPortRequestPowerStateChange, AtaPortRequestPowerStateChange routine [Storage Devices], irb/AtaPortRequestPowerStateChange, storage.ataportrequestpowerstatechange
ms.topic: function
f1_keywords:
 - "irb/AtaPortRequestPowerStateChange"
req.header: irb.h
req.include-header: Ata.h, Irb.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Irb.h
api_name:
- AtaPortRequestPowerStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortRequestPowerStateChange function


## -description


The <b>AtaPortRequestPowerStateChange</b> routine requests a power state transition for the indicated device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension

A pointer to the channel extension. 


### -param TargetId

Specifies the target identifier of the device. 


### -param Lun

Specifies the logical unit number (LUN). 


### -param DesiredPowerState

Contains an enumerator value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ne-irb-ide_power_state">IDE_POWER_STATE</a> that indicates the power state to which the indicated device should be changed. 


## -remarks



The <b>AtaPortRequestPowerStateChange</b> routine is used when a miniport driver might have to initiate a power state change, such as when a hot-plug operation occurs. 

<div class="alert"><b>Note</b>   The practice of doing idle detection from an ATA miniport driver is discouraged. </div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ne-irb-ide_power_state">IDE_POWER_STATE</a>
 

 

