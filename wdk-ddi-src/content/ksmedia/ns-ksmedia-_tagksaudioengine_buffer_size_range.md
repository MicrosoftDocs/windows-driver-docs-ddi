---
UID: NS:ksmedia._tagKSAUDIOENGINE_BUFFER_SIZE_RANGE
title: "_tagKSAUDIOENGINE_BUFFER_SIZE_RANGE"
author: windows-driver-content
description: The KSAUDIOENGINE_BUFFER_SIZE_RANGE structure specifies the minimum and maximum buffer size that the hardware audio engine can support at the instance when it is called.
old-location: audio\ksaudio_buffer_limits.htm
old-project: audio
ms.assetid: 7BFF1B51-9559-471C-868C-F3E861CB4914
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_tagKSAUDIOENGINE_BUFFER_SIZE_RANGE, ksmedia/PKSAUDIOENGINE_BUFFER_SIZE_RANGE, *PKSAUDIOENGINE_BUFFER_SIZE_RANGE, KSAUDIOENGINE_BUFFER_SIZE_RANGE structure [Audio Devices], KSAUDIOENGINE_BUFFER_SIZE_RANGE, audio.ksaudio_buffer_limits, PKSAUDIOENGINE_BUFFER_SIZE_RANGE, ksmedia/KSAUDIOENGINE_BUFFER_SIZE_RANGE, PKSAUDIOENGINE_BUFFER_SIZE_RANGE structure pointer [Audio Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSAUDIOENGINE_BUFFER_SIZE_RANGE
product: Windows
targetos: Windows
req.typenames: "*PKSAUDIOENGINE_BUFFER_SIZE_RANGE, KSAUDIOENGINE_BUFFER_SIZE_RANGE"
---

# _tagKSAUDIOENGINE_BUFFER_SIZE_RANGE structure


## -description


The <b>KSAUDIOENGINE_BUFFER_SIZE_RANGE</b> structure specifies the minimum and maximum buffer size that the hardware audio engine can support at the instance when it is called.


## -syntax


````
typedef struct _KSAUDIO_BUFFER_SIZE_RANGE {
  ULONG MaxBufferBytes;
  ULONG MinBufferBytes;
} KSAUDIOENGINE_BUFFER_SIZE_RANGE, *PKSAUDIOENGINE_BUFFER_SIZE_RANGE;
````


## -struct-fields




### -field MinBufferBytes

Specifies the minimum buffer size in bytes that the hardware Audio Engine can support, at the instance when it is called. The minimum size is calculated to be the minimum size of buffer that will not cause frequent audio glitching.


### -field MaxBufferBytes

Specifies the maximun available DMA buffer size in bytes that the hardware Audio Engine can support, at the instance when it is called.  The capability and availability  of the DMA engine and the internal DSP buffer are all taken into consideration.


## -remarks



The audio stack uses the information about the buffer size limits to determine the optimum buffer size to allocate, to achieve low power playback. The audio stack also takes into account the data format that the caller specified in the <a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a> structure when it called the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450868">KSPROPERTY_AUDIOENGINE_BUFFER_SIZE_RANGE</a> property.




## -see-also

<a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450868">KSPROPERTY_AUDIOENGINE_BUFFER_SIZE_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450867">KSPROPERTY_AUDIOENGINE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIOENGINE_BUFFER_SIZE_RANGE structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

