---
UID: NF:irb.AtaPortWriteRegisterUchar
title: AtaPortWriteRegisterUchar function (irb.h)
description: The AtaPortWriteRegisterUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisteruchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortWriteRegisterUchar function"]
ms.keywords: AtaPortWriteRegisterUchar, AtaPortWriteRegisterUchar routine [Storage Devices], atartns_14d5eb64-a6b7-4eb4-94f6-0bd0952d2263.xml, irb/AtaPortWriteRegisterUchar, storage.ataportwriteregisteruchar
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
 - AtaPortWriteRegisterUchar
 - irb/AtaPortWriteRegisterUchar
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
 - AtaPortWriteRegisterUchar
---

# AtaPortWriteRegisterUchar function


## -description

The <b>AtaPortWriteRegisterUchar</b> routine transfers an unsigned byte to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
A pointer to the destination register. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

### -param Value 

[in]
Specifies the value to write to the register for the HBA.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteregisterulong">AtaPortWriteRegisterUlong</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteregisterushort">AtaPortWriteRegisterUshort</a>
