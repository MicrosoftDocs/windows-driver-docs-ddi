---
UID: NF:portcls.IPortWaveRTStream.FreePagesFromMdl
title: IPortWaveRTStream::FreePagesFromMdl
author: windows-driver-content
description: The FreePagesFromMdl method frees a memory descriptor list (MDL).
old-location: audio\iportwavertstream_freepagesfrommdl.htm
old-project: audio
ms.assetid: 8839c0ab-08c5-4cc7-a526-aa1ebe2fde15
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FreePagesFromMdl, FreePagesFromMdl method [Audio Devices], FreePagesFromMdl method [Audio Devices],IPortWaveRTStream interface, IPortWaveRTStream interface [Audio Devices],FreePagesFromMdl method, IPortWaveRTStream.FreePagesFromMdl, IPortWaveRTStream::FreePagesFromMdl, audio.iportwavertstream_freepagesfrommdl, audmp-routines_7e3477c5-08b8-4e7c-bfb9-36945bf765c4.xml, portcls/IPortWaveRTStream::FreePagesFromMdl
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
-	IPortWaveRTStream.FreePagesFromMdl
product: Windows
targetos: Windows
req.typenames: 
---

# IPortWaveRTStream::FreePagesFromMdl


## -description


The <code>FreePagesFromMdl</code> method frees a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>).


## -parameters




### -param MemoryDescriptorList [in]

Pointer to the MDL.


## -returns



None




## -remarks



The miniport driver must call this method to free an MDL that was previously allocated by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>.

<code>FreePagesFromMdl</code> frees both the physical memory pages described in the MDL and the MDL itself. On return, the MDL pointer value in the <i>MemoryDescriptorList</i> parameter is no longer valid.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/976f7e83-9b2a-4e1b-ab76-76d8e9711bff">IPortWaveRTStream::AllocateContiguousPagesForMdl </a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>
 

 

