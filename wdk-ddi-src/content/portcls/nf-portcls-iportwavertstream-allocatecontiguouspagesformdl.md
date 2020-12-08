---
UID: NF:portcls.IPortWaveRTStream.AllocateContiguousPagesForMdl
title: IPortWaveRTStream::AllocateContiguousPagesForMdl (portcls.h)
description: The AllocateContiguousPagesForMdl method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them.
old-location: audio\iportwavertstream_allocatecontiguouspagesformdl.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortWaveRTStream::AllocateContiguousPagesForMdl"]
ms.keywords: AllocateContiguousPagesForMdl, AllocateContiguousPagesForMdl method [Audio Devices], AllocateContiguousPagesForMdl method [Audio Devices],IPortWaveRTStream interface, IPortWaveRTStream interface [Audio Devices],AllocateContiguousPagesForMdl method, IPortWaveRTStream.AllocateContiguousPagesForMdl, IPortWaveRTStream::AllocateContiguousPagesForMdl, audio.iportwavertstream_allocatecontiguouspagesformdl, audmp-routines_92ff395d-072b-4a11-b856-3afc1a024289.xml, portcls/IPortWaveRTStream::AllocateContiguousPagesForMdl
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortWaveRTStream::AllocateContiguousPagesForMdl
 - portcls/IPortWaveRTStream::AllocateContiguousPagesForMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IPortWaveRTStream.AllocateContiguousPagesForMdl
---

# IPortWaveRTStream::AllocateContiguousPagesForMdl


## -description

The <code>AllocateContiguousPagesForMdl</code> method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>) that describes them.

## -parameters

### -param LowAddress 

[in]
Specifies the low end of the address range from which the storage for the MDL can be allocated.

### -param HighAddress 

[in]
Specifies the high end of the address range from which the storage for the MDL can be allocated.

### -param TotalBytes 

[in]
Specifies the total number of bytes to allocate for the MDL. This method always allocates an integral number of memory pages.

## -returns

<code>AllocateContiguousPagesForMdl</code> returns a pointer to an MDL (PMDL) that describes a list of physical memory pages. If the method is unable to allocate the requested buffer, it returns <b>NULL</b>.

## -remarks

The driver calls this method to allocate a block of physically contiguous memory pages. All of the physical memory pages in the MDL fall within the address range specified by the <i>LowAddress</i> and <i>HighAddress</i> parameters. If sufficient memory is available, the memory allocation is the requested size rounded up to the next page; otherwise, the call fails.

After a system has been running for some time, the system's pool of nonpaged memory tends to become fragmented, which increases the probability that a request to allocate a large block of contiguous physical memory will fail. If the DMA controller of the audio device does not require the physical memory pages to be contiguous, the driver must call <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl</a> instead. Unlike <code>AllocateContiguousPagesForMdl</code>, the <b>AllocatePagesForMdl</b> method is not affected by memory fragmentation.

The <code>AllocateContiguousPagesforMdl</code> method allocates memory pages that are locked (nonpaged) but unmapped. If the miniport driver requires software access to this memory, the miniport driver must make a subsequent call to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-mapallocatedpages">IPortWaveRTStream::MapAllocatedPages</a> to map the pages into kernel-mode address space.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavertstream">IPortWaveRTStream</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-mapallocatedpages">IPortWaveRTStream::MapAllocatedPages</a>
