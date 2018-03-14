---
UID: NF:portcls.IPortWaveRTStream.AllocatePagesForMdl
title: IPortWaveRTStream::AllocatePagesForMdl method
author: windows-driver-content
description: The AllocatePagesForMdl method allocates a list of nonpaged physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them.
old-location: audio\iportwavertstream_allocatepagesformdl.htm
old-project: audio
ms.assetid: 44839b9e-f206-49e6-a9f6-14e79d1e0ae2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AllocatePagesForMdl method [Audio Devices], AllocatePagesForMdl method [Audio Devices], IPortWaveRTStream interface, AllocatePagesForMdl,IPortWaveRTStream.AllocatePagesForMdl, IPortWaveRTStream, IPortWaveRTStream interface [Audio Devices], AllocatePagesForMdl method, IPortWaveRTStream::AllocatePagesForMdl, audio.iportwavertstream_allocatepagesformdl, audmp-routines_2722e5c2-7fd2-4b72-acbf-474313bca229.xml, portcls/IPortWaveRTStream::AllocatePagesForMdl
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
req.lib: 
req.dll: 
req.irql: Passive level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortWaveRTStream.AllocatePagesForMdl
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWaveRTStream::AllocatePagesForMdl method


## -description


The <code>AllocatePagesForMdl</code> method allocates a list of nonpaged physical memory pages and returns a pointer to a memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>) that describes them.


## -syntax


````
PMDL AllocatePagesForMdl(
  [in] PHYSICAL_ADDRESS HighAddress,
  [in] SIZE_T           TotalBytes
);
````


## -parameters




### -param HighAddress [in]

Specifies the high end of the address range from which the storage for the MDL can be allocated. The low end of the address range is implicitly zero.


### -param TotalBytes [in]

Specifies the total number of bytes to allocate for the MDL. This method always allocates an integral number of memory pages.


## -returns



<code>AllocatePagesforMdl</code> returns a pointer to an MDL that describes a list of physical memory pages. If the method is unable to allocate the requested buffer, it returns <b>NULL</b>.




## -remarks



Since the Windows audio stack does not support a mechanism to express memory access alignment requirements for buffers, audio drivers must select a caching type for mapped memory buffers that does not impose platform-specific alignment requirements. In other words, the caching type used by the audio driver for mapped memory buffers, must not make assumptions about the memory alignment requirements for any specific platform.

The driver calls this method to allocate memory that can be mapped to user or kernel mode. The physical memory pages in the MDL are not necessarily contiguous in physical memory, but they all fall within the specified address range.

The method always allocates an integral number of pages. If sufficient memory is available, the memory allocation is the requested size rounded up to the next page. Otherwise, the memory allocation can be less than the requested size. The caller must verify how many bytes are actually allocated.

If the DMA controller of the audio device requires the physical memory pages in the buffer to be contiguous, the driver must call <a href="https://msdn.microsoft.com/976f7e83-9b2a-4e1b-ab76-76d8e9711bff">IPortWaveRTStream::AllocateContiguousPagesForMdl </a> instead.

Like the <a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl </a> function, the <code>AllocatePagesforMdl</code> method allocates memory pages that are locked (nonpaged) but unmapped. If the miniport driver wants to set up software access to this memory, the miniport driver must make a subsequent call to <a href="https://msdn.microsoft.com/90f412de-073f-4889-adf3-898cde0206b7">IPortWaveRTStream::MapAllocatedPages </a> to map the pages into kernel-mode address space. 




## -see-also

<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



 

 


