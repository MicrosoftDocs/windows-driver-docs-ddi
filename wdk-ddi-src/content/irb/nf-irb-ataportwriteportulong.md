---
UID: NF:irb.AtaPortWritePortUlong
title: AtaPortWritePortUlong function (irb.h)
description: The AtaPortWritePortUlong routine transfers a ULONG value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportulong.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortWritePortUlong function"]
ms.keywords: AtaPortWritePortUlong, AtaPortWritePortUlong routine [Storage Devices], atartns_4930ccb8-61a2-415e-897a-6e3ef573e623.xml, irb/AtaPortWritePortUlong, storage.ataportwriteportulong
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
 - AtaPortWritePortUlong
 - irb/AtaPortWritePortUlong
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
 - AtaPortWritePortUlong
---

# AtaPortWritePortUlong function


## -description

The <b>AtaPortWritePortUlong</b> routine transfers a ULONG value to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port [in]


A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

### -param Value [in]


Specifies the value to write to the HBA's I/O port.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportuchar">AtaPortWritePortUchar</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportushort">AtaPortWritePortUshort</a>
