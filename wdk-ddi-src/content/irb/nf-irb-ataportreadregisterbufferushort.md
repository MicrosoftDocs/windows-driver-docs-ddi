---
UID: NF:irb.AtaPortReadRegisterBufferUshort
title: AtaPortReadRegisterBufferUshort function (irb.h)
description: The AtaPortReadRegisterBufferUshort routine transfers a specified number of USHORT values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterbufferushort.htm
tech.root: storage
ms.assetid: bd2e8fe0-7daf-4fdd-ac3a-893df6d0f10f
ms.date: 03/29/2018
keywords: ["AtaPortReadRegisterBufferUshort function"]
ms.keywords: AtaPortReadRegisterBufferUshort, AtaPortReadRegisterBufferUshort routine [Storage Devices], atartns_4943b97d-90a0-44d9-adfa-d3bce57e88c9.xml, irb/AtaPortReadRegisterBufferUshort, storage.ataportreadregisterbufferushort
f1_keywords:
 - "irb/AtaPortReadRegisterBufferUshort"
 - "AtaPortReadRegisterBufferUshort"
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
- AtaPortReadRegisterBufferUshort
targetos: Windows
req.typenames: 
---

# AtaPortReadRegisterBufferUshort function


## -description


The <b>AtaPortReadRegisterBufferUshort</b> routine transfers a specified number of USHORT values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register 
[in]
Contains the register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.


### -param Buffer 
[in]
A pointer to the destination buffer. 


### -param Count 
[in]
Specifies the number of USHORT values to read from the HBA.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterbufferuchar">AtaPortReadRegisterBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterbufferulong">AtaPortReadRegisterBufferUlong</a>
 

 

