---
UID: NF:irb.AtaPortReadRegisterUchar
title: AtaPortReadRegisterUchar function (irb.h)
description: The AtaPortReadRegisterUchar routine reads an unsigned byte value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisteruchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortReadRegisterUchar function"]
ms.keywords: AtaPortReadRegisterUchar, AtaPortReadRegisterUchar routine [Storage Devices], atartns_63ee26b2-b436-4dc6-a3aa-5a13691e85dd.xml, irb/AtaPortReadRegisterUchar, storage.ataportreadregisteruchar
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
 - AtaPortReadRegisterUchar
 - irb/AtaPortReadRegisterUchar
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
 - AtaPortReadRegisterUchar
---

# AtaPortReadRegisterUchar function


## -description

The <b>AtaPortReadRegisterUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register [in]


A pointer to the register to read. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

## -returns

<b>AtaPortReadRegisterUchar</b> returns a UCHAR value from the HBA's register.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterulong">AtaPortReadRegisterUlong</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterushort">AtaPortReadRegisterUshort</a>
