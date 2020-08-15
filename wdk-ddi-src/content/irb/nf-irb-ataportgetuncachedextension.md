---
UID: NF:irb.AtaPortGetUnCachedExtension
title: AtaPortGetUnCachedExtension function (irb.h)
description: The AtaPortGetUncachedExtension routine allocates an uncached common buffer that is shared by the CPU and the device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportgetuncachedextension.htm
tech.root: storage
ms.assetid: 7b81fc29-4906-4095-b197-6b63f5f01ac0
ms.date: 03/29/2018
keywords: ["AtaPortGetUnCachedExtension function"]
ms.keywords: AtaPortGetUnCachedExtension, AtaPortGetUnCachedExtension routine [Storage Devices], atartns_30b7c0f0-5636-4d81-b1de-13d8c413f4d6.xml, irb/AtaPortGetUnCachedExtension, storage.ataportgetuncachedextension
f1_keywords:
 - "irb/AtaPortGetUnCachedExtension"
 - "AtaPortGetUnCachedExtension"
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ataport.lib
- ataport.dll
- pciidex.lib
- pciidex.dll
api_name:
- AtaPortGetUnCachedExtension
targetos: Windows
req.typenames: 
---

# AtaPortGetUnCachedExtension function


## -description


The <b>AtaPortGetUncachedExtension</b> routine allocates an uncached common buffer that is shared by the CPU and the device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension 
[in]
A pointer to the channel extension. 


### -param UncachedExtensionSize 
[in]
Specifies the length, in bytes, of the uncached common buffer. Set this parameter to 0 if the miniport driver does not require an uncached extension.


### -param IrbExtensionSize 
[in]
Specifies the size, in bytes, that is required by the miniport driver for its per request storage, if any. 

Set this parameter set to 0 if the miniport driver does not maintain per IRB information for which it requires storage. 


## -returns



<b>AtaPortGetUncachedExtension</b> returns a virtual address pointer to the uncached extension. If it cannot allocate the requested memory, or if the memory was previously allocated, it returns <b>NULL</b>.




## -remarks



The miniport driver can use IRB extensions as storage for driver-determined, request-specific information, such as data that is necessary to process a particular request.

The port driver does not initialize IRB extensions, but sets a pointer to an extension in each IRB that it sends to the miniport driver.

HBA hardware can safely access an IRB extension.

The miniport driver must not call <b>AtaPortGetUncachedExtension</b> from any routine other than its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a> routine, and only when it is processing a control action of <b>StartChannel</b>. Calls of <b>AtaPortGetUncachedExtension</b> from other miniport driver routines result in incorrect operation or even system failure. The port driver automatically frees the uncached extension after it invokes <b>IdeHwControl</b> with the <b>StopChannel</b> control action.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a>
 

 

