---
UID: NS:ksmedia.KSAUDIO_POSITIONEX
title: KSAUDIO_POSITIONEX
author: windows-driver-content
description: The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver.
old-location: audio\ksaudio_positionex.htm
old-project: audio
ms.assetid: 63cd938c-1ccd-4f67-a4eb-2898002ae762
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PKSAUDIO_POSITIONEX, KSAUDIO_POSITIONEX, KSAUDIO_POSITIONEX structure [Audio Devices], PKSAUDIO_POSITIONEX, PKSAUDIO_POSITIONEX structure pointer [Audio Devices], aud-prop_9a418d76-9a4f-4626-b6db-64ed4fcedb18.xml, audio.ksaudio_positionex, ksmedia/KSAUDIO_POSITIONEX, ksmedia/PKSAUDIO_POSITIONEX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	ksmedia.h
apiname:
-	KSAUDIO_POSITIONEX
product: Windows
targetos: Windows
req.typenames: KSAUDIO_POSITIONEX, *PKSAUDIO_POSITIONEX
---

# KSAUDIO_POSITIONEX structure


## -description


The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver.


## -syntax


````
typedef struct {
  LARGE_INTEGER    TimerFrequency;
  LARGE_INTEGER    TimeStamp1;
  KSAUDIO_POSITION Position;
  LARGE_INTEGER    TimeStamp2;
} KSAUDIO_POSITIONEX, *PKSAUDIO_POSITIONEX;
````


## -struct-fields




### -field TimerFrequency

Specifies the number of ticks per second for the timer that produces the timestamps.


### -field TimeStamp1

Specifies the timestamp that is taken immediately prior to the acquisition of the position information.


### -field Position

Specifies the position of the read cursor and the write cursor in the audio buffer of an audio stream.


### -field TimeStamp2

Specifies the timestamp that is taken immediately after the acquisition of the position information.


## -remarks



A KS-based audio driver can use the KSAUDIO_POSITIONEX structure along with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537298">KSPROPERTY_AUDIO_POSITIONEX</a> property to return a stream position and a timestamp.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537298">KSPROPERTY_AUDIO_POSITIONEX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_POSITIONEX structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

