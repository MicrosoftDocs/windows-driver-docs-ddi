---
UID: NF:irb.AtaPortWritePortUchar
title: AtaPortWritePortUchar function (irb.h)
description: The AtaPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportuchar.htm
tech.root: storage
ms.assetid: 2585da94-babe-479f-8957-adaa9190451e
ms.date: 03/29/2018
keywords: ["AtaPortWritePortUchar function"]
ms.keywords: AtaPortWritePortUchar, AtaPortWritePortUchar routine [Storage Devices], atartns_25e284e4-0c1e-4172-b0d2-4435e23f7270.xml, irb/AtaPortWritePortUchar, storage.ataportwriteportuchar
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
 - AtaPortWritePortUchar
 - irb/AtaPortWritePortUchar
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
 - AtaPortWritePortUchar
---

# AtaPortWritePortUchar function


## -description

The <b>AtaPortWritePortUchar</b> routine transfers an unsigned byte to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port 

[in]
A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

### -param Value 

[in]
Specifies the value to write to the HBA's I/O port

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportulong">AtaPortWritePortUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportushort">AtaPortWritePortUshort</a>

