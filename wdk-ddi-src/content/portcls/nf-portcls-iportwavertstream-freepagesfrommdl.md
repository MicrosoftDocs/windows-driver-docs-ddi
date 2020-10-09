---
UID: NF:portcls.IPortWaveRTStream.FreePagesFromMdl
title: IPortWaveRTStream::FreePagesFromMdl (portcls.h)
description: The FreePagesFromMdl method frees a memory descriptor list (MDL).
old-location: audio\iportwavertstream_freepagesfrommdl.htm
tech.root: audio
ms.assetid: 8839c0ab-08c5-4cc7-a526-aa1ebe2fde15
ms.date: 05/08/2018
keywords: ["IPortWaveRTStream::FreePagesFromMdl"]
ms.keywords: FreePagesFromMdl, FreePagesFromMdl method [Audio Devices], FreePagesFromMdl method [Audio Devices],IPortWaveRTStream interface, IPortWaveRTStream interface [Audio Devices],FreePagesFromMdl method, IPortWaveRTStream.FreePagesFromMdl, IPortWaveRTStream::FreePagesFromMdl, audio.iportwavertstream_freepagesfrommdl, audmp-routines_7e3477c5-08b8-4e7c-bfb9-36945bf765c4.xml, portcls/IPortWaveRTStream::FreePagesFromMdl
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortWaveRTStream::FreePagesFromMdl
 - portcls/IPortWaveRTStream::FreePagesFromMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IPortWaveRTStream.FreePagesFromMdl
---

# IPortWaveRTStream::FreePagesFromMdl


## -description

The <code>FreePagesFromMdl</code> method frees a memory descriptor list (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>).

## -parameters

### -param MemoryDescriptorList 

[in]
Pointer to the MDL.

## -remarks

The miniport driver must call this method to free an MDL that was previously allocated by calling either <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl</a> or <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatecontiguouspagesformdl">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>.

<code>FreePagesFromMdl</code> frees both the physical memory pages described in the MDL and the MDL itself. On return, the MDL pointer value in the <i>MemoryDescriptorList</i> parameter is no longer valid.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavertstream">IPortWaveRTStream</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatecontiguouspagesformdl">IPortWaveRTStream::AllocateContiguousPagesForMdl </a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl</a>