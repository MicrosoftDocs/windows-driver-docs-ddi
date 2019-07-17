---
UID: NF:irb.AtaPortReadPortBufferUlong
title: AtaPortReadPortBufferUlong function (irb.h)
description: The AtaPortReadPortBufferUlong routine transfers a given number of ULONG values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportbufferulong.htm
tech.root: storage
ms.assetid: ff70685f-f3cf-49c0-bb0b-02e561feeac3
ms.date: 03/29/2018
ms.keywords: AtaPortReadPortBufferUlong, AtaPortReadPortBufferUlong routine [Storage Devices], atartns_e2f251c9-d2a0-4b33-91d8-2d700eb4253e.xml, irb/AtaPortReadPortBufferUlong, storage.ataportreadportbufferulong
ms.topic: function
f1_keywords:
 - "irb/AtaPortReadPortBufferUlong"
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
- AtaPortReadPortBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReadPortBufferUlong function


## -description


The <b>AtaPortReadPortBufferUlong</b> routine transfers a given number of ULONG values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the destination buffer.


### -param Count [in]

Specifies the number of ULONG values to read from the HBA.


## -returns



None 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportreadportbufferuchar">AtaPortReadPortBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportreadportbufferushort">AtaPortReadPortBufferUshort</a>
 

 

