---
UID: NF:portcls.IPortWaveRTStream.MapAllocatedPages
title: IPortWaveRTStream::MapAllocatedPages method
author: windows-driver-content
description: The MapAllocatedPages method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode.
old-location: audio\iportwavertstream_mapallocatedpages.htm
old-project: audio
ms.assetid: 90f412de-073f-4889-adf3-898cde0206b7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: audio.iportwavertstream_mapallocatedpages, IPortWaveRTStream::MapAllocatedPages, IPortWaveRTStream interface [Audio Devices], MapAllocatedPages method, IPortWaveRTStream, portcls/IPortWaveRTStream::MapAllocatedPages, MapAllocatedPages, MapAllocatedPages method [Audio Devices], IPortWaveRTStream interface, audmp-routines_914e2039-e45b-44c5-8b29-0bcc6da901c3.xml, MapAllocatedPages method [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: Passive level.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortWaveRTStream.MapAllocatedPages
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWaveRTStream::MapAllocatedPages method


## -description


The <code>MapAllocatedPages</code> method maps a list of previously allocated physical pages into a contiguous block of virtual memory that is accessible from kernel-mode.


## -syntax


````
PVOID MapAllocatedPages(
  [in] PMDL                MemoryDescriptorList,
  [in] MEMORY_CACHING_TYPE CacheType
);
````


## -parameters




### -param MemoryDescriptorList [in]

Pointer to the memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>) that will be mapped. The MDL can be allocated by calling either <a href="https://msdn.microsoft.com/44839b9e-f206-49e6-a9f6-14e79d1e0ae2">IPortWaveRTStream::AllocatePagesForMdl </a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>.


### -param CacheType [in]

Specifies the cache type. Set this parameter to one of the following <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> enumeration values: <b>MmNonCached</b>, <b>MmCached</b>, or <b>MmWriteCombined</b>.


## -returns



<code>MapAllocatedPages</code> returns the starting address of the mapped buffer in virtual memory. If the method is unable to map the buffer, it returns <b>NULL</b>.




## -remarks



Since the Windows audio stack does not support a mechanism to express memory access alignment requirements for buffers, audio drivers must select a caching type for mapped memory buffers that does not impose platform-specific alignment requirements. In other words, the caching type used by the audio driver for mapped memory buffers, must not make assumptions about the memory alignment requirements for any specific platform.

This method maps the physical memory pages in the MDL  into kernel-mode virtual memory. Typically, the miniport driver calls this method if it requires software access to the scatter-gather list for an audio buffer. In this case, the storage for the scatter-gather list must have been allocated by the <b>IPortWaveRTStream::AllocatePagesForMdl</b> or <b>IPortWaveRTStream::AllocateContiguousPagesForMdl</b> method. 

A WaveRT miniport driver should not require software access to the audio buffer itself.

<code>MapAllocatedPages</code> is similar in operation to the <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> function. The miniport driver is responsible for unmapping the memory prior to freeing it. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536934">IPortWaveRTStream::UnmapAllocatedPages</a>.




## -see-also

<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>



<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536934">IPortWaveRTStream::UnmapAllocatedPages</a>



<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



<a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::MapAllocatedPages method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

