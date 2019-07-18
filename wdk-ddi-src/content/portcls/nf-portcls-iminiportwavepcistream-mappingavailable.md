---
UID: NF:portcls.IMiniportWavePciStream.MappingAvailable
title: IMiniportWavePciStream::MappingAvailable (portcls.h)
description: The MappingAvailable method indicates that a new mapping is available.
old-location: audio\iminiportwavepcistream_mappingavailable.htm
tech.root: audio
ms.assetid: 11126cc9-43a1-41b1-adc9-13af57157d74
ms.date: 05/08/2018
ms.keywords: IMiniportWavePciStream interface [Audio Devices],MappingAvailable method, IMiniportWavePciStream.MappingAvailable, IMiniportWavePciStream::MappingAvailable, MappingAvailable, MappingAvailable method [Audio Devices], MappingAvailable method [Audio Devices],IMiniportWavePciStream interface, audio.iminiportwavepcistream_mappingavailable, audmp-routines_931efc43-ec71-4b60-905a-47ec374da31e.xml, portcls/IMiniportWavePciStream::MappingAvailable
ms.topic: method
f1_keywords:
 - "portcls/IMiniportWavePciStream.MappingAvailable"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IMiniportWavePciStream.MappingAvailable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::MappingAvailable


## -description


The <code>MappingAvailable</code> method indicates that a new mapping is available.


## -parameters






#### - None


## -returns



None




## -remarks



The port driver calls the <code>MappingAvailable</code> method to notify the miniport driver that a new mapping has become available, but it does so only when the miniport driver's previous request for mapping through <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a> has been refused.

The port driver (Portcls.sys) can call the <code>MappingAvailable</code> method at any level equal to or below DISPATCH_LEVEL, depending on the circumstances under which the call is made. As a result, the <code>MappingAvailable</code> method must be in a non-paged code segment and can only touch non-paged code.

See the discussion of allocator framing in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wavepci-latency">WavePci Latency</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>
 

 

