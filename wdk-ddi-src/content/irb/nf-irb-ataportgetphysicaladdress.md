---
UID: NF:irb.AtaPortGetPhysicalAddress
title: AtaPortGetPhysicalAddress function (irb.h)
description: The AtaPortGetPhysicalAddress routine converts the virtual address range to the physical address range.
old-location: storage\ataportgetphysicaladdress.htm
tech.root: storage
ms.assetid: f6c595f2-a493-453a-a744-7ce6577ae29e
ms.date: 03/29/2018
keywords: ["AtaPortGetPhysicalAddress function"]
ms.keywords: AtaPortGetPhysicalAddress, AtaPortGetPhysicalAddress routine [Storage Devices], atartns_8067117e-f163-4fe9-a3f4-24b32b5bcf63.xml, irb/AtaPortGetPhysicalAddress, storage.ataportgetphysicaladdress
f1_keywords:
 - "irb/AtaPortGetPhysicalAddress"
 - "AtaPortGetPhysicalAddress"
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
- AtaPortGetPhysicalAddress
targetos: Windows
req.typenames: 
---

# AtaPortGetPhysicalAddress function


## -description


The <b>AtaPortGetPhysicalAddress</b> routine converts the virtual address range to the physical address range. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param Irb [in, optional]

A pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) for which the address range is converted. 


### -param VirtualAddress [in, optional]

A pointer to the base virtual address to convert. 


### -param Length [out, optional]

Returns the number of mapped bytes starting at the returned physical address. 


## -returns



<b>AtaPortGetPhysicalAddress </b>returns the corresponding physical address for the virtual address. If the virtual address cannot be converted, it returns <b>NULL</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a>
 

 

