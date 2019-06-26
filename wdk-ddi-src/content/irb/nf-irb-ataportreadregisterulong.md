---
UID: NF:irb.AtaPortReadRegisterUlong
title: AtaPortReadRegisterUlong function (irb.h)
description: The AtaPortReadRegisterUlong routine reads a ULONG value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterulong.htm
tech.root: storage
ms.assetid: c824bbbe-0f51-48b4-b7df-aa8a84f1f982
ms.date: 03/29/2018
ms.keywords: AtaPortReadRegisterUlong, AtaPortReadRegisterUlong routine [Storage Devices], atartns_a5e1a904-214d-45fc-9ade-fc5ad7d56694.xml, irb/AtaPortReadRegisterUlong, storage.ataportreadregisterulong
ms.topic: function
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
- AtaPortReadRegisterUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReadRegisterUlong function


## -description


The <b>AtaPortReadRegisterUlong</b> routine reads a ULONG value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

A pointer to the register to read. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.


## -returns



<b>AtaPortReadRegisterUlong</b> returns a ULONG value from the HBA's register. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportreadregisteruchar">AtaPortReadRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportreadregisterushort">AtaPortReadRegisterUshort</a>
 

 

