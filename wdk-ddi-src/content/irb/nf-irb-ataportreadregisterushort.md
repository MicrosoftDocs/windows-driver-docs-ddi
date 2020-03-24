---
UID: NF:irb.AtaPortReadRegisterUshort
title: AtaPortReadRegisterUshort function (irb.h)
description: The AtaPortReadRegisterUshort routine reads a USHORT value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterushort.htm
tech.root: storage
ms.assetid: a0a9792c-a2a1-4079-9e1c-c41c5b872fa0
ms.date: 03/29/2018
keywords: ["AtaPortReadRegisterUshort function"]
ms.keywords: AtaPortReadRegisterUshort, AtaPortReadRegisterUshort routine [Storage Devices], atartns_4173b6fd-0784-4279-ae9e-d51469a000c6.xml, irb/AtaPortReadRegisterUshort, storage.ataportreadregisterushort
f1_keywords:
 - "irb/AtaPortReadRegisterUshort"
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
- AtaPortReadRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReadRegisterUshort function


## -description


The <b>AtaPortReadRegisterUshort</b> routine reads a USHORT value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

A pointer to the register to be read. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.


## -returns



<b>AtaPortReadRegisterUshort</b> returns a USHORT value from the HBA's register. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisteruchar">AtaPortReadRegisterUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterulong">AtaPortReadRegisterUlong</a>
 

 

