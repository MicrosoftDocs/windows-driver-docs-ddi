---
UID: NF:irb.AtaPortMoveMemory
title: AtaPortMoveMemory function (irb.h)
description: The AtaPortMoveMemory routine copies data from one location to another.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportmovememory.htm
tech.root: storage
ms.assetid: c9d724bb-cc65-428c-ad48-21b227f3c8b1
ms.date: 03/29/2018
ms.keywords: AtaPortMoveMemory, AtaPortMoveMemory routine [Storage Devices], atartns_9ecea2c5-892f-4d04-9865-30598ac4e5d6.xml, irb/AtaPortMoveMemory, storage.ataportmovememory
ms.topic: function
f1_keywords:
 - "irb/AtaPortMoveMemory"
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
- AtaPortMoveMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortMoveMemory function


## -description


The <b>AtaPortMoveMemory</b> routine copies data from one location to another.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param WriteBuffer [out]

A pointer to the destination buffer.


### -param ReadBuffer [in]

A pointer to the source buffer.


### -param Length [in]

Specifies the number of bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>.


## -returns



None 




## -remarks



The miniport driver calls the <b>AtaPortMoveMemory</b> routine to copy data from one system-allocated area to another. 

The location pointed to by <i>ReadBuffer</i> and <i>Length</i> can overlap the range of addresses between <i>WriteBuffer</i> and <i>Length</i>. 



