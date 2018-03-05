---
UID: NF:portcls.IPortWaveRTStream.GetPhysicalPageAddress
title: IPortWaveRTStream::GetPhysicalPageAddress method
author: windows-driver-content
description: The GetPhysicalPageAddress method returns the physical address for a page within a memory descriptor list (MDL).
old-location: audio\iportwavertstream_getphysicalpageaddress.htm
old-project: audio
ms.assetid: 24c22102-f91d-4ea1-81fb-98052b8d0153
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetPhysicalPageAddress method [Audio Devices], GetPhysicalPageAddress method [Audio Devices], IPortWaveRTStream interface, GetPhysicalPageAddress,IPortWaveRTStream.GetPhysicalPageAddress, IPortWaveRTStream, IPortWaveRTStream interface [Audio Devices], GetPhysicalPageAddress method, IPortWaveRTStream::GetPhysicalPageAddress, audio.iportwavertstream_getphysicalpageaddress, audmp-routines_44b6b9ed-368b-4bf1-9a21-e0e0b2b90728.xml, portcls/IPortWaveRTStream::GetPhysicalPageAddress
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
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWaveRTStream::GetPhysicalPageAddress method


## -description


The <code>GetPhysicalPageAddress</code> method returns the physical address for a page within a memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>).


## -syntax


````
PHYSICAL_ADDRESS GetPhysicalPageAddress(
  [in] PMDL  MemoryDescriptorList,
  [in] ULONG Index
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>



<a href="https://msdn.microsoft.com/8126af29-a7ee-4ab7-8902-45b4baf33b9e">IPortWaveRTStream::GetPhysicalPagesCount </a>



<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::GetPhysicalPageAddress method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

