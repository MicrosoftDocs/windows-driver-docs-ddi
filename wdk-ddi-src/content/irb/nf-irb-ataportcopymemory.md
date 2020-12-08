---
UID: NF:irb.AtaPortCopyMemory
title: AtaPortCopyMemory function (irb.h)
description: The AtaPortCopyMemory routine copies data from one location to another.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportcopymemory.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortCopyMemory function"]
ms.keywords: AtaPortCopyMemory, AtaPortCopyMemory routine [Storage Devices], atartns_7aa7f4e2-4c74-403e-bbdf-795973a9846b.xml, irb/AtaPortCopyMemory, storage.ataportcopymemory
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
 - AtaPortCopyMemory
 - irb/AtaPortCopyMemory
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
 - AtaPortCopyMemory
---

# AtaPortCopyMemory function


## -description

The <b>AtaPortCopyMemory</b> routine copies data from one location to another.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param WriteBuffer 

[out]
A pointer to the destination buffer.

### -param ReadBuffer 

[in]
A pointer to the source buffer.

### -param Length 

[in]
Specifies the number of bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>.

## -remarks

The miniport driver calls the <b>AtaPortCopy</b><b>Memory</b> routine to copy data from one system-allocated area to another.
