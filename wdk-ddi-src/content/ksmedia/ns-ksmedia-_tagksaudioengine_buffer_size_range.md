---
UID: NS:ksmedia._tagKSAUDIOENGINE_BUFFER_SIZE_RANGE
title: _tagKSAUDIOENGINE_BUFFER_SIZE_RANGE (ksmedia.h)
description: The KSAUDIOENGINE_BUFFER_SIZE_RANGE structure specifies the minimum and maximum buffer size that the hardware audio engine can support at the instance when it is called.
old-location: audio\ksaudio_buffer_limits.htm
tech.root: audio
ms.assetid: 7BFF1B51-9559-471C-868C-F3E861CB4914
ms.date: 05/08/2018
ms.keywords: "*PKSAUDIOENGINE_BUFFER_SIZE_RANGE, KSAUDIOENGINE_BUFFER_SIZE_RANGE, KSAUDIOENGINE_BUFFER_SIZE_RANGE structure [Audio Devices], PKSAUDIOENGINE_BUFFER_SIZE_RANGE, PKSAUDIOENGINE_BUFFER_SIZE_RANGE structure pointer [Audio Devices], _tagKSAUDIOENGINE_BUFFER_SIZE_RANGE, audio.ksaudio_buffer_limits, ksmedia/KSAUDIOENGINE_BUFFER_SIZE_RANGE, ksmedia/PKSAUDIOENGINE_BUFFER_SIZE_RANGE"
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
- Ksmedia.h
api_name:
- KSAUDIOENGINE_BUFFER_SIZE_RANGE
product:
- Windows
targetos: Windows
req.typenames: KSAUDIOENGINE_BUFFER_SIZE_RANGE, *PKSAUDIOENGINE_BUFFER_SIZE_RANGE
---

# _tagKSAUDIOENGINE_BUFFER_SIZE_RANGE structure


## -description


The <b>KSAUDIOENGINE_BUFFER_SIZE_RANGE</b> structure specifies the minimum and maximum buffer size that the hardware audio engine can support at the instance when it is called.


## -struct-fields




### -field MinBufferBytes

Specifies the minimum buffer size in bytes that the hardware Audio Engine can support, at the instance when it is called. The minimum size is calculated to be the minimum size of buffer that will not cause frequent audio glitching.


### -field MaxBufferBytes

Specifies the maximun available DMA buffer size in bytes that the hardware Audio Engine can support, at the instance when it is called.  The capability and availability  of the DMA engine and the internal DSP buffer are all taken into consideration.


## -remarks



The audio stack uses the information about the buffer size limits to determine the optimum buffer size to allocate, to achieve low power playback. The audio stack also takes into account the data format that the caller specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a> structure when it called the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450868">KSPROPERTY_AUDIOENGINE_BUFFER_SIZE_RANGE</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450867">KSPROPERTY_AUDIOENGINE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450868">KSPROPERTY_AUDIOENGINE_BUFFER_SIZE_RANGE</a>
 

 

