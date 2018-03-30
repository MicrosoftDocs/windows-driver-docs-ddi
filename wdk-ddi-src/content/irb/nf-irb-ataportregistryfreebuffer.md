---
UID: NF:irb.AtaPortRegistryFreeBuffer
title: AtaPortRegistryFreeBuffer function
author: windows-driver-content
description: The AtaPortRegistryFreeBuffer routine frees the registry buffer that was allocated by using AtaPortRegistryAllocateBuffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportregistryfreebuffer.htm
old-project: storage
ms.assetid: a84dffce-977e-412a-a12a-e0e156b943ac
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortRegistryFreeBuffer, AtaPortRegistryFreeBuffer routine [Storage Devices], atartns_70807844-dbef-4457-bd47-102aeffcc840.xml, irb/AtaPortRegistryFreeBuffer, storage.ataportregistryfreebuffer
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
api_name:
-	AtaPortRegistryFreeBuffer
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRegistryFreeBuffer function


## -description


The <b>AtaPortRegistryFreeBuffer</b> routine frees the registry buffer that was allocated by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param Buffer [in]

A pointer to the buffer to free. 


## -returns



None




## -remarks



<b>AtaPortRegistryFreeBuffer</b> flushes deferred write operations to the registry.

The miniport driver must call <b>AtaPortRegistryFreeBuffer</b> either in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a> routine or in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine. It cannot call <b>AtaPortRegistryFreeBuffer</b> from any other routine. Additionally, the miniport driver can only call <b>AtaPortRegistryFreeBuffer</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550200">AtaPortRegistryAllocateBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>
 

 

