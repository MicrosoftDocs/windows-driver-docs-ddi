---
UID: NF:irb.AtaPortRegistryAllocateBuffer
title: AtaPortRegistryAllocateBuffer function
author: windows-driver-content
description: The AtaPortRegistryAllocateBuffer routine allocates a buffer for registry operations.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportregistryallocatebuffer.htm
old-project: storage
ms.assetid: c888fd84-2828-4f2d-921d-ba92a5ce9c84
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortRegistryAllocateBuffer, AtaPortRegistryAllocateBuffer routine [Storage Devices], atartns_9ad4a954-9252-4128-99b9-a82e89da5f98.xml, irb/AtaPortRegistryAllocateBuffer, storage.ataportregistryallocatebuffer
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
-	AtaPortRegistryAllocateBuffer
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRegistryAllocateBuffer function


## -description


The <b>AtaPortRegistryAllocateBuffer</b> routine allocates a buffer for registry operations.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
PVOID AtaPortRegistryAllocateBuffer(
  _In_ PVOID ChannelExtension,
  _In_ ULONG Count
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param BufferSize

TBD




#### - Count [in]

Specifies the length of the buffer, in bytes.


## -returns



<b>AtaPortRegistryAllocateBuffer</b> returns a pointer to the allocated buffer on success. Otherwise, it returns <b>NULL</b>. 




## -remarks



The port driver enables the miniport driver to allocate one buffer for all its registry operations. After the miniport driver has allocated a buffer with <b>AtaPortRegistryAllocateBuffer</b>, later calls to <b>AtaPortRegistryAllocateBuffer</b> will fail and return <b>NULL</b>. After the miniport driver frees the allocated buffer with a call to the <a href="..\irb\nf-irb-ataportregistryfreebuffer.md">AtaPortRegistryFreeBuffer</a> routine, it can again allocate buffers by calling <b>AtaPortRegistryAllocateBuffer</b>.

The miniport driver must call <b>AtaPortRegistryAllocateBuffer</b> either in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a> routine or in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine. It cannot call <b>AtaPortRegistryAllocateBuffer</b> from any other routine. Additionally, the miniport driver can only call <b>AtaPortRegistryAllocateBuffer</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 




## -see-also

<a href="..\irb\nf-irb-ataportregistryfreebuffer.md">AtaPortRegistryFreeBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550141">AtaChannelInitRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRegistryAllocateBuffer routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

