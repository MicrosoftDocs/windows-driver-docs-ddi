---
UID: NF:irb.AtaPortWritePortBufferUchar
title: AtaPortWritePortBufferUchar function (irb.h)
description: The AtaPortWritePortBufferUchar routine transfers the indicated number of unsigned bytes from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportbufferuchar.htm
tech.root: storage
ms.assetid: 43c12b35-380c-46bc-9ea0-9745f047c81a
ms.date: 03/29/2018
keywords: ["AtaPortWritePortBufferUchar function"]
ms.keywords: AtaPortWritePortBufferUchar, AtaPortWritePortBufferUchar routine [Storage Devices], atartns_a1c82429-9d44-4a9b-8285-e632172a6be4.xml, irb/AtaPortWritePortBufferUchar, storage.ataportwriteportbufferuchar
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
 - AtaPortWritePortBufferUchar
 - irb/AtaPortWritePortBufferUchar
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
 - AtaPortWritePortBufferUchar
---

# AtaPortWritePortBufferUchar function


## -description

The <b>AtaPortWritePortBufferUchar</b> routine transfers the indicated number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port 

[in]
Pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

### -param Buffer 

[in]
A pointer to the source buffer.

### -param Count 

[in]
Specifies the number of UCHAR values to write to the HBA.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportbufferulong">AtaPortWritePortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportwriteportbufferushort">AtaPortWritePortBufferUshort</a>

