---
UID: NF:irb.AtaPortConvertUlongToPhysicalAddress
title: AtaPortConvertUlongToPhysicalAddress function (irb.h)
description: The AtaPortConvertUlongToPhysicalAddress routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportconvertulongtophysicaladdress.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortConvertUlongToPhysicalAddress function"]
ms.keywords: AtaPortConvertUlongToPhysicalAddress, AtaPortConvertUlongToPhysicalAddress routine [Storage Devices], atartns_29b4ce0d-5dda-4203-a10b-66ccd7859d5d.xml, irb/AtaPortConvertUlongToPhysicalAddress, storage.ataportconvertulongtophysicaladdress
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
 - AtaPortConvertUlongToPhysicalAddress
 - irb/AtaPortConvertUlongToPhysicalAddress
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
 - AtaPortConvertUlongToPhysicalAddress
---

# AtaPortConvertUlongToPhysicalAddress function


## -description

The <b>AtaPortConvertUlongToPhysicalAddress</b> routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param UlongAddress 

[in]
Specifies a value of type ULONG.

## -returns

<b>AtaPortConvertUlongToPhysicalAddress</b> returns the converted IDE_PHYSICAL_ADDRESS value.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportconvertphysicaladdresstoulong">AtaPortConvertPhysicalAddressToUlong</a>
