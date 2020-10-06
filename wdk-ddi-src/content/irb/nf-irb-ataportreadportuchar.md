---
UID: NF:irb.AtaPortReadPortUchar
title: AtaPortReadPortUchar function (irb.h)
description: The AtaPortReadPortUchar routine reads an unsigned byte value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportuchar.htm
tech.root: storage
ms.assetid: 9be74e98-ba68-492c-9660-43b2f76052cd
ms.date: 03/29/2018
keywords: ["AtaPortReadPortUchar function"]
ms.keywords: AtaPortReadPortUchar, AtaPortReadPortUchar routine [Storage Devices], atartns_6ac346ce-b2cd-4c50-b55f-1c952a01e736.xml, irb/AtaPortReadPortUchar, storage.ataportreadportuchar
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
 - AtaPortReadPortUchar
 - irb/AtaPortReadPortUchar
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
 - AtaPortReadPortUchar
---

# AtaPortReadPortUchar function


## -description

The <b>AtaPortReadPortUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port 

[in]
A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

## -returns

<b>AtaPortReadPortUchar</b> returns a UCHAR value from the HBA's I/O port.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadportulong">AtaPortReadPortUlong</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadportushort">AtaPortReadPortUshort</a>