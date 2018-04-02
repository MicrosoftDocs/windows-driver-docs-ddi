---
UID: NF:portcls.IPortWaveRTStream.UnmapAllocatedPages
title: IPortWaveRTStream::UnmapAllocatedPages method
author: windows-driver-content
description: The UnmapAllocatedPages method releases a mapping.
old-location: audio\iportwavertstream_unmapallocatedpages.htm
old-project: audio
ms.assetid: 558636ed-4bab-42bc-8925-df01e032439a
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortWaveRTStream, IPortWaveRTStream interface [Audio Devices], UnmapAllocatedPages method, IPortWaveRTStream::UnmapAllocatedPages, UnmapAllocatedPages method [Audio Devices], UnmapAllocatedPages method [Audio Devices], IPortWaveRTStream interface, UnmapAllocatedPages,IPortWaveRTStream.UnmapAllocatedPages, audio.iportwavertstream_unmapallocatedpages, audmp-routines_2d402b1b-6951-48db-89bb-81f3cc7e0076.xml, portcls/IPortWaveRTStream::UnmapAllocatedPages
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
req.irql: Passive level.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortWaveRTStream.UnmapAllocatedPages
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWaveRTStream::UnmapAllocatedPages method


## -description


The <code>UnmapAllocatedPages</code> method releases a mapping.


## -parameters




### -param BaseAddress [in]

Pointer to the base virtual address to which the physical pages were mapped.


### -param MemoryDescriptorList [in]

Pointer to a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>) that describes the physical pages.


## -returns



None




## -remarks



The miniport driver must call this method to release a mapping that was set up by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a>. The driver must release the mapping before calling <a href="https://msdn.microsoft.com/8839c0ab-08c5-4cc7-a526-aa1ebe2fde15">IPortWaveRTStream::FreePagesFromMdl </a> to free the MDL.

This method is similar in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556391">MmUnmapLockedPages</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536926">IPortWaveRTStream::FreePagesFromMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556391">MmUnmapLockedPages</a>
 

 

