---
UID: NS:ksmedia.KSAUDIO_POSITION
title: KSAUDIO_POSITION
author: windows-driver-content
description: The KSAUDIO_POSITION structure specifies the current positions of the play and write cursors in the sound buffer for an audio stream.
old-location: audio\ksaudio_position.htm
old-project: audio
ms.assetid: 91658dfc-dad4-4fbb-8688-13971e7275e2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: aud-prop_0518af7c-0c1d-4710-8879-43bb42e1ba2a.xml, audio.ksaudio_position, KSAUDIO_POSITION, ksmedia/KSAUDIO_POSITION, KSAUDIO_POSITION structure [Audio Devices], ksmedia/PKSAUDIO_POSITION, PKSAUDIO_POSITION structure pointer [Audio Devices], *PKSAUDIO_POSITION, PKSAUDIO_POSITION
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
-	KSAUDIO_POSITION
product: Windows
targetos: Windows
req.typenames: "*PKSAUDIO_POSITION, KSAUDIO_POSITION"
---

# KSAUDIO_POSITION structure


## -description


The KSAUDIO_POSITION structure specifies the current positions of the play and write cursors in the sound buffer for an audio stream.


## -syntax


````
typedef struct {
  ULONGLONG PlayOffset;
  ULONGLONG WriteOffset;
  DWORDLONG PlayOffset;
  DWORDLONG WriteOffset;
} KSAUDIO_POSITION, *PKSAUDIO_POSITION;
````


## -struct-fields




#### - PlayOffset

Specifies the current play position as a byte offset.

Specifies the current play position as a byte offset.


#### - WriteOffset

Specifies the current write position as a byte offset.

Specifies the current write position as a byte offset.


## -remarks


This structure is used to get and set the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a> property.

For a looped client buffer (with stream type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563381">KSINTERFACE_STANDARD_LOOPED_STREAMING</a>), <b>PlayOffset</b> and <b>WriteOffset</b> are byte offsets into the client buffer. When either offset reaches the end of the buffer, it wraps around to the start of the buffer. Hence, neither offset ever exceeds the buffer size.

For a nonlooped client buffer (with stream type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563384">KSINTERFACE_STANDARD_STREAMING</a>), <b>PlayOffset</b> and <b>WriteOffset</b> are not offsets into any one physical buffer that either your driver has allocated or a client has allocated. Instead, these offsets are stream-relative and can be thought of as offsets into an idealized buffer that contains the entire stream and is contiguous from beginning to end. Any internal offsets that point into the actual physical buffers that contain the data need to be maintained separately.

During playback, the <b>PlayOffset</b> and <b>WriteOffset</b> values are interpreted as follows:
<ul>
<li>
<b>PlayOffset</b> is the offset of the last byte in the buffer that has played. <b>PlayOffset</b> + 1 is the offset of the next byte that will play.

</li>
<li>
<b>WriteOffset</b> is the offset of the last byte in the playback buffer.

</li>
</ul>When a client submits another buffer to the device for playback, <b>WriteOffset</b> will increment upon receipt of that buffer to indicate the new <b>WriteOffset</b> value, but <b>PlayOffset</b> does not change until after that buffer has actually been played by the device.

During recording, the <b>PlayOffset</b> and <b>WriteOffset</b> values are interpreted as follows:
<ul>
<li>
<b>PlayOffset</b> is the offset of the last byte in the buffer that has been captured. <b>PlayOffset</b> + 1 is the offset of the next byte that will be captured.

</li>
<li>
<b>WriteOffset</b> is the offset of the last byte in the capture buffer.

</li>
</ul>When an application submits another buffer to the device for capturing, the <b>WriteOffset</b> value will increment upon receipt of that buffer. The <b>PlayOffset</b> value will not change until data has actually been captured into the buffer.

The space between <b>PlayOffset</b> and <b>WriteOffset</b> is considered off-limits to the client because it represents the portion of the client buffer that has already been sent to the driver and might still be in use by the driver.

For more information, see <a href="https://msdn.microsoft.com/893fea84-9136-4107-96d2-8a4e2ab7bd2a">Audio Position Property</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563384">KSINTERFACE_STANDARD_STREAMING</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563381">KSINTERFACE_STANDARD_LOOPED_STREAMING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_POSITION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

