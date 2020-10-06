---
UID: NF:irb.AtaPortRegistryAllocateBuffer
title: AtaPortRegistryAllocateBuffer function (irb.h)
description: The AtaPortRegistryAllocateBuffer routine allocates a buffer for registry operations.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportregistryallocatebuffer.htm
tech.root: storage
ms.assetid: c888fd84-2828-4f2d-921d-ba92a5ce9c84
ms.date: 03/29/2018
keywords: ["AtaPortRegistryAllocateBuffer function"]
ms.keywords: AtaPortRegistryAllocateBuffer, AtaPortRegistryAllocateBuffer routine [Storage Devices], atartns_9ad4a954-9252-4128-99b9-a82e89da5f98.xml, irb/AtaPortRegistryAllocateBuffer, storage.ataportregistryallocatebuffer
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
 - AtaPortRegistryAllocateBuffer
 - irb/AtaPortRegistryAllocateBuffer
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
 - AtaPortRegistryAllocateBuffer
---

# AtaPortRegistryAllocateBuffer function


## -description

The <b>AtaPortRegistryAllocateBuffer</b> routine allocates a buffer for registry operations.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param ChannelExtension 

[in]
A pointer to the channel extension.

### -param BufferSize

<p>Specifies the length of the buffer, in bytes.</p>

## -returns

<b>AtaPortRegistryAllocateBuffer</b> returns a pointer to the allocated buffer on success. Otherwise, it returns <b>NULL</b>.

## -remarks

The port driver enables the miniport driver to allocate one buffer for all its registry operations. After the miniport driver has allocated a buffer with <b>AtaPortRegistryAllocateBuffer</b>, later calls to <b>AtaPortRegistryAllocateBuffer</b> will fail and return <b>NULL</b>. After the miniport driver frees the allocated buffer with a call to the <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistryfreebuffer">AtaPortRegistryFreeBuffer</a> routine, it can again allocate buffers by calling <b>AtaPortRegistryAllocateBuffer</b>.

The miniport driver must call <b>AtaPortRegistryAllocateBuffer</b> either in its <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a> routine or in its <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a> routine. It cannot call <b>AtaPortRegistryAllocateBuffer</b> from any other routine. Additionally, the miniport driver can only call <b>AtaPortRegistryAllocateBuffer</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportregistryfreebuffer">AtaPortRegistryFreeBuffer</a>



<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a>