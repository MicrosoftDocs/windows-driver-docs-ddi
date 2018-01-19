---
UID: NS:ksmedia.KSAUDIO_DYNAMIC_RANGE
title: KSAUDIO_DYNAMIC_RANGE
author: windows-driver-content
description: The KSAUDIO_DYNAMIC_RANGE structure specifies the dynamic range of an audio stream. This structure is used to get or set the data value for the KSPROPERTY_AUDIO_DYNAMIC_RANGE property.
old-location: audio\ksaudio_dynamic_range.htm
old-project: audio
ms.assetid: 4bf5c95f-dc08-4d1e-8e52-6d0de19df4c0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSAUDIO_DYNAMIC_RANGE, *PKSAUDIO_DYNAMIC_RANGE, KSAUDIO_DYNAMIC_RANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_DYNAMIC_RANGE
req.alt-loc: ksmedia.h
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
req.typenames: *PKSAUDIO_DYNAMIC_RANGE, KSAUDIO_DYNAMIC_RANGE
---

# KSAUDIO_DYNAMIC_RANGE structure



## -description
The KSAUDIO_DYNAMIC_RANGE structure specifies the dynamic range of an audio stream. This structure is used to get or set the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537281">KSPROPERTY_AUDIO_DYNAMIC_RANGE</a> property.



## -syntax

````
typedef struct {
  ULONG QuietCompression;
  ULONG LoudCompression;
} KSAUDIO_DYNAMIC_RANGE, *PKSAUDIO_DYNAMIC_RANGE;
````


## -struct-fields

### -field QuietCompression

Specifies the compression level for soft sounds. This value ranges from 0 to 100 percent (represented as 0xFFFFFFFF) of the linear range compression for soft sounds. The higher this value, the higher the volume of soft sounds.


### -field LoudCompression

Specifies the compression level for loud sounds. This value ranges from 0 to 100 percent (represented as 0xFFFFFFFF) of the linear range compression for loud sounds. The higher this value, the lower the volume of loud sounds.


## -remarks
By default, both structure members are set to zero percent, which reproduces the full dynamic range of the audio stream.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537281">KSPROPERTY_AUDIO_DYNAMIC_RANGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_DYNAMIC_RANGE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

