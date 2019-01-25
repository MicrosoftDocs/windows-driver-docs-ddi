---
UID: NF:portcls.IPortWaveRTStream.GetPhysicalPageAddress
title: IPortWaveRTStream::GetPhysicalPageAddress (portcls.h)
description: The GetPhysicalPageAddress method returns the physical address for a page within a memory descriptor list (MDL).
old-location: audio\iportwavertstream_getphysicalpageaddress.htm
tech.root: audio
ms.assetid: 24c22102-f91d-4ea1-81fb-98052b8d0153
ms.date: 05/08/2018
ms.keywords: GetPhysicalPageAddress, GetPhysicalPageAddress method [Audio Devices], GetPhysicalPageAddress method [Audio Devices],IPortWaveRTStream interface, IPortWaveRTStream interface [Audio Devices],GetPhysicalPageAddress method, IPortWaveRTStream.GetPhysicalPageAddress, IPortWaveRTStream::GetPhysicalPageAddress, audio.iportwavertstream_getphysicalpageaddress, audmp-routines_44b6b9ed-368b-4bf1-9a21-e0e0b2b90728.xml, portcls/IPortWaveRTStream::GetPhysicalPageAddress
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
-	IPortWaveRTStream.GetPhysicalPageAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWaveRTStream::GetPhysicalPageAddress


## -description


The <code>GetPhysicalPageAddress</code> method returns the physical address for a page within a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>).


## -parameters




### -param MemoryDescriptorList [in]

Pointer to the MDL.


### -param Index [in]

Index to the target page within the MDL.


## -returns



The <code>GetPhysicalPageAddress</code> method returns the physical address for a page within an MDL.




## -remarks



The miniport driver calls this method to determine the physical memory address for pages within an MDL that was previously allocated by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a> or <b>IPortWaveRTStream::AllocateContiguousPagesForMdl</b>.

The miniport typically calls this for each page in the MDL in order to program the physical address into the DMA.  The <i>Index</i> parameter is used to select the desired page, and can range from zero to the count returned by <a href="https://msdn.microsoft.com/8126af29-a7ee-4ab7-8902-45b4baf33b9e">GetPhysicalPagesCount</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>



<a href="https://msdn.microsoft.com/8126af29-a7ee-4ab7-8902-45b4baf33b9e">IPortWaveRTStream::GetPhysicalPagesCount </a>
 

 

