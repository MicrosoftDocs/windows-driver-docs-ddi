---
UID: NF:irb.AtaPortWritePortUshort
title: AtaPortWritePortUshort function (irb.h)
description: The AtaPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportushort.htm
tech.root: storage
ms.assetid: 14b47f0a-5de8-4650-8a90-40e9da8537f1
ms.date: 03/29/2018
keywords: ["AtaPortWritePortUshort function"]
ms.keywords: AtaPortWritePortUshort, AtaPortWritePortUshort routine [Storage Devices], atartns_1766efcd-f235-43ae-8fbe-ab56a858a7ee.xml, irb/AtaPortWritePortUshort, storage.ataportwriteportushort
f1_keywords:
 - "irb/AtaPortWritePortUshort"
 - "AtaPortWritePortUshort"
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
- AtaPortWritePortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortWritePortUshort function


## -description


The <b>AtaPortWritePortUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.


### -param Value [in]

Specifies the value to write to the HBA's I/O port.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportuchar">AtaPortWritePortUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportulong">AtaPortWritePortUlong</a>
 

 

