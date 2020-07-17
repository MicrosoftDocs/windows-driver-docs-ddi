---
UID: NS:ksmedia.__unnamed_struct_25
title: KSRTAUDIO_BUFFER (ksmedia.h)
description: The KSRTAUDIO_BUFFER structure specifies the buffer address, size, and a call memory barrier flag for a cyclic audio data buffer.
old-location: audio\ksrtaudio_buffer.htm
tech.root: audio
ms.assetid: b80efaf0-ecee-40cd-befb-2139a20840a5
ms.date: 05/08/2018
keywords: ["KSRTAUDIO_BUFFER structure"]
ms.keywords: "*PKSRTAUDIO_BUFFER, KSRTAUDIO_BUFFER, KSRTAUDIO_BUFFER structure [Audio Devices], PKSRTAUDIO_BUFFER, PKSRTAUDIO_BUFFER structure pointer [Audio Devices], aud-prop_50b4ab60-2e9a-444b-98d3-984d9084ab0b.xml, audio.ksrtaudio_buffer, ksmedia/KSRTAUDIO_BUFFER, ksmedia/PKSRTAUDIO_BUFFER"
f1_keywords:
 - "ksmedia/KSRTAUDIO_BUFFER"
 - "KSRTAUDIO_BUFFER"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSRTAUDIO_BUFFER
product:
- Windows
targetos: Windows
req.typenames: KSRTAUDIO_BUFFER, *PKSRTAUDIO_BUFFER
---

# KSRTAUDIO_BUFFER structure


## -description


The KSRTAUDIO_BUFFER structure specifies the buffer address, size, and a call memory barrier flag for a cyclic audio data buffer.


## -struct-fields




### -field BufferAddress

Specifies the base address of the cyclic buffer. This is a virtual memory address through which the user-mode client can directly access the buffer. The driver writes the actual base address of the allocated buffer into this member.


### -field ActualBufferSize

Specifies the buffer size, in bytes. The driver sets this member to the actual size of the allocated buffer.


### -field CallMemoryBarrier

Specifies a flag based on cache type of the allocated buffer. The driver sets this flag to <b>TRUE</b> if the cache type is <b>MmWriteCombined</b>; otherwise, the flag should be set to <b>FALSE</b>. For more information about <b>MmWriteCombined</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE </a>,


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer">KSPROPERTY_RTAUDIO_BUFFER</a> request uses the KSRTAUDIO_BUFFER structure to describe the actual cyclic buffer that the driver allocates. This client fills in a <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksrtaudio-buffer-property">KSRTAUDIO_BUFFER_PROPERTY</a> structure to request the audio buffer, and the driver fills in a KSRTAUDIO_BUFFER structure with the results from the buffer allocation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer">KSPROPERTY_RTAUDIO_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksrtaudio-buffer-property">KSRTAUDIO_BUFFER_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a>
 

 

