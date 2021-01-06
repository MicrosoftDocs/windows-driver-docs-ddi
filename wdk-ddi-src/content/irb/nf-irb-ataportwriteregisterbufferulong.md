---
UID: NF:irb.AtaPortWriteRegisterBufferUlong
title: AtaPortWriteRegisterBufferUlong function (irb.h)
description: The AtaPortWriteRegisterBufferUlong routine transfers the indicated number of ULONG values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterbufferulong.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortWriteRegisterBufferUlong function"]
ms.keywords: AtaPortWriteRegisterBufferUlong, AtaPortWriteRegisterBufferUlong routine [Storage Devices], atartns_678d25ba-ba41-4a94-b689-5f19a89ace7f.xml, irb/AtaPortWriteRegisterBufferUlong, storage.ataportwriteregisterbufferulong
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
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortWriteRegisterBufferUlong
 - irb/AtaPortWriteRegisterBufferUlong
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
 - AtaPortWriteRegisterBufferUlong
---

# AtaPortWriteRegisterBufferUlong function


## -description

The <b>AtaPortWriteRegisterBufferUlong</b> routine transfers the indicated number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Contains the destination register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses at are obtained by a call to <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

### -param Buffer 

[in]
A pointer to the source buffer.

### -param Count 

[in]
Specifies the number of ULONG values to write to the HBA.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteregisterbufferuchar">AtaPortWriteRegisterBufferUchar</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteregisterbufferushort">AtaPortWriteRegisterBufferUshort</a>
