---
UID: NF:portcls.IMiniportWaveCyclicStream.Silence
title: IMiniportWaveCyclicStream::Silence (portcls.h)
description: The Silence method is used to copy silence samples to a specified buffer.
old-location: audio\iminiportwavecyclicstream_silence.htm
tech.root: audio
ms.assetid: e2acf3f5-d054-44c4-8ab9-ffd1b934f700
ms.date: 05/08/2018
keywords: ["IMiniportWaveCyclicStream::Silence"]
ms.keywords: IMiniportWaveCyclicStream interface [Audio Devices],Silence method, IMiniportWaveCyclicStream.Silence, IMiniportWaveCyclicStream::Silence, Silence, Silence method [Audio Devices], Silence method [Audio Devices],IMiniportWaveCyclicStream interface, audio.iminiportwavecyclicstream_silence, audmp-routines_860013ac-d79b-4b11-91b7-1a7bc3c84a5b.xml, portcls/IMiniportWaveCyclicStream::Silence
f1_keywords:
 - "portcls/IMiniportWaveCyclicStream.Silence"
 - "IMiniportWaveCyclicStream.Silence"
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWaveCyclicStream.Silence
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclicStream::Silence


## -description


The <code>Silence</code> method is used to copy silence samples to a specified buffer.


## -parameters




### -param Buffer 
[in]
Pointer in kernel virtual-address space to the start of the buffer to which the silence samples are to be written. The buffer must be large enough to contain at least the number of bytes specified in <i>ByteCount</i>.


### -param ByteCount 
[in]
Specifies the number of bytes of silence to be written to the buffer.


## -returns



<code>Silence</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Windows treats 8-bit PCM values as unsigned, and it treats 16-bit and larger PCM values as signed. When filling a portion of an 8-bit PCM buffer with silence, the <code>Silence</code> method sets each byte to the value 0x80. When writing silence to a buffer containing 16-bit or larger PCM values, the method fills the specified portion of the buffer with zeros.



