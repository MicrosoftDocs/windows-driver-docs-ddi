---
UID: NF:portcls.IMiniportWaveCyclicStream.SetFormat
title: IMiniportWaveCyclicStream::SetFormat (portcls.h)
description: The SetFormat method sets the KS data format of the wave stream.
old-location: audio\iminiportwavecyclicstream_setformat.htm
tech.root: audio
ms.assetid: 6881ea55-138a-408e-955e-c5c74f777ce8
ms.date: 05/08/2018
keywords: ["IMiniportWaveCyclicStream::SetFormat"]
ms.keywords: IMiniportWaveCyclicStream interface [Audio Devices],SetFormat method, IMiniportWaveCyclicStream.SetFormat, IMiniportWaveCyclicStream::SetFormat, SetFormat, SetFormat method [Audio Devices], SetFormat method [Audio Devices],IMiniportWaveCyclicStream interface, audio.iminiportwavecyclicstream_setformat, audmp-routines_d23a09d4-7110-425f-b10d-5f7f601179bb.xml, portcls/IMiniportWaveCyclicStream::SetFormat
f1_keywords:
 - "portcls/IMiniportWaveCyclicStream.SetFormat"
 - "IMiniportWaveCyclicStream.SetFormat"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWaveCyclicStream.SetFormat
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclicStream::SetFormat


## -description


The <code>SetFormat</code> method sets the KS data format of the wave stream.


## -parameters




### -param DataFormat [in]

Specifies the new format of the stream. This parameter is a pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>.


## -returns



<code>SetFormat</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The wave stream's initial format is specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a> call that creates the stream. Following stream creation, the <code>SetFormat</code> call can change the stream's format from its initial setting.

For information about specifying wave stream formats, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-data-formats-and-data-ranges">Audio Data Formats and Data Ranges</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclicstream">IMiniportWaveCyclicStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>
 

 

