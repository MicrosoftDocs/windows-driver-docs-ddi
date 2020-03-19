---
UID: NF:portcls.IPortWaveRTStream.MapAllocatedPages
title: IPortWaveRTStream::MapAllocatedPages (portcls.h)
description: The MapAllocatedPages method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode.
old-location: audio\iportwavertstream_mapallocatedpages.htm
tech.root: audio
ms.assetid: 90f412de-073f-4889-adf3-898cde0206b7
ms.date: 05/08/2018
keywords: ["IPortWaveRTStream::MapAllocatedPages"]
ms.keywords: IPortWaveRTStream interface [Audio Devices],MapAllocatedPages method, IPortWaveRTStream.MapAllocatedPages, IPortWaveRTStream::MapAllocatedPages, MapAllocatedPages, MapAllocatedPages method [Audio Devices], MapAllocatedPages method [Audio Devices],IPortWaveRTStream interface, audio.iportwavertstream_mapallocatedpages, audmp-routines_914e2039-e45b-44c5-8b29-0bcc6da901c3.xml, portcls/IPortWaveRTStream::MapAllocatedPages
f1_keywords:
 - "portcls/IPortWaveRTStream.MapAllocatedPages"
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: Passive level.
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IPortWaveRTStream.MapAllocatedPages
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWaveRTStream::MapAllocatedPages


## -description


The <code>MapAllocatedPages</code> method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode.


## -parameters




### -param MemoryDescriptorList [in]

Pointer to the memory descriptor list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>) that will be mapped. The MDL can be allocated by calling either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl </a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatecontiguouspagesformdl">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>.


### -param CacheType [in]

Specifies the cache type. Set this parameter to one of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> enumeration values: <b>MmNonCached</b>, <b>MmCached</b>, or <b>MmWriteCombined</b>.


## -returns



<code>MapAllocatedPages</code> returns the starting address of the mapped buffer in virtual memory. If the method is unable to map the buffer, it returns <b>NULL</b>.




## -remarks



Since the Windows audio stack does not support a mechanism to express memory access alignment requirements for buffers, audio drivers must select a caching type for mapped memory buffers that does not impose platform-specific alignment requirements. In other words, the caching type used by the audio driver for mapped memory buffers, must not make assumptions about the memory alignment requirements for any specific platform.

This method maps the physical memory pages in the MDL  into kernel-mode virtual memory. Typically, the miniport driver calls this method if it requires software access to the scatter-gather list for an audio buffer. In this case, the storage for the scatter-gather list must have been allocated by the <b>IPortWaveRTStream::AllocatePagesForMdl</b> or <b>IPortWaveRTStream::AllocateContiguousPagesForMdl</b> method. 

A WaveRT miniport driver should not require software access to the audio buffer itself.

<code>MapAllocatedPages</code> is similar in operation to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a> function. The miniport driver is responsible for unmapping the memory prior to freeing it. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-unmapallocatedpages">IPortWaveRTStream::UnmapAllocatedPages</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavertstream">IPortWaveRTStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatecontiguouspagesformdl">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-unmapallocatedpages">IPortWaveRTStream::UnmapAllocatedPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>
 

 

