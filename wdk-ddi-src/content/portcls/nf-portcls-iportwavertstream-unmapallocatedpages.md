---
UID: NF:portcls.IPortWaveRTStream.UnmapAllocatedPages
title: IPortWaveRTStream::UnmapAllocatedPages (portcls.h)
description: The UnmapAllocatedPages method releases a mapping.
old-location: audio\iportwavertstream_unmapallocatedpages.htm
tech.root: audio
ms.assetid: 558636ed-4bab-42bc-8925-df01e032439a
ms.date: 05/08/2018
keywords: ["IPortWaveRTStream::UnmapAllocatedPages"]
ms.keywords: IPortWaveRTStream interface [Audio Devices],UnmapAllocatedPages method, IPortWaveRTStream.UnmapAllocatedPages, IPortWaveRTStream::UnmapAllocatedPages, UnmapAllocatedPages, UnmapAllocatedPages method [Audio Devices], UnmapAllocatedPages method [Audio Devices],IPortWaveRTStream interface, audio.iportwavertstream_unmapallocatedpages, audmp-routines_2d402b1b-6951-48db-89bb-81f3cc7e0076.xml, portcls/IPortWaveRTStream::UnmapAllocatedPages
f1_keywords:
 - "portcls/IPortWaveRTStream.UnmapAllocatedPages"
 - "IPortWaveRTStream.UnmapAllocatedPages"
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
- IPortWaveRTStream.UnmapAllocatedPages
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWaveRTStream::UnmapAllocatedPages


## -description


The <code>UnmapAllocatedPages</code> method releases a mapping.


## -parameters




### -param BaseAddress [in]

Pointer to the base virtual address to which the physical pages were mapped.


### -param MemoryDescriptorList [in]

Pointer to a memory descriptor list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>) that describes the physical pages.


## -remarks



The miniport driver must call this method to release a mapping that was set up by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-mapallocatedpages">IPortWaveRTStream::MapAllocatedPages</a>. The driver must release the mapping before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-freepagesfrommdl">IPortWaveRTStream::FreePagesFromMdl </a> to free the MDL.

This method is similar in operation to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a> function. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavertstream">IPortWaveRTStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-freepagesfrommdl">IPortWaveRTStream::FreePagesFromMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-mapallocatedpages">IPortWaveRTStream::MapAllocatedPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a>
 

 

