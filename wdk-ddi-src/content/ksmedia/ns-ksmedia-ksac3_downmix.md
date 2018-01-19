---
UID: NS:ksmedia.KSAC3_DOWNMIX
title: KSAC3_DOWNMIX
author: windows-driver-content
description: The KSAC3_DOWNMIX structure specifies whether the program channels in an AC-3-encoded stream need to be downmixed to accommodate the speaker configuration.
old-location: audio\ksac3_downmix.htm
old-project: audio
ms.assetid: d35450ec-5ddc-4312-bd77-ab7e89690f82
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSAC3_DOWNMIX, *PKSAC3_DOWNMIX, KSAC3_DOWNMIX
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
req.alt-api: KSAC3_DOWNMIX
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
req.typenames: *PKSAC3_DOWNMIX, KSAC3_DOWNMIX
---

# KSAC3_DOWNMIX structure



## -description
The KSAC3_DOWNMIX structure specifies whether the program channels in an AC-3-encoded stream need to be downmixed to accommodate the speaker configuration.



## -syntax

````
typedef struct {
  BOOL fDownMix;
  BOOL fDolbySurround;
} KSAC3_DOWNMIX, *PKSAC3_DOWNMIX;
````


## -struct-fields

### -field fDownMix

Specifies whether to downmix. If <b>TRUE</b>, downmixing to fewer channels is enabled. The number of output channels depends on the number of speakers present (as specified by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a> property). If <b>FALSE</b>, input and output channels are mapped to speakers on a one-to-one basis. In other words, input channel 0 is mapped to output channel 0, input channel 1 is mapped to output channel 1, and so on, up to the number of encoded channels or speakers, whichever is smaller.


### -field fDolbySurround

Specifies how the output channels are encoded. If <b>TRUE</b>, the output channels are first encoded as two Dolby Surround Pro Logic channels, Lt and Rt. If <b>FALSE</b>, the output channels do not use Dolby Surround Pro Logic encoding.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537218">KSPROPERTY_AC3_DOWNMIX</a> property.

For information about the mapping of output channels to speakers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537218">KSPROPERTY_AC3_DOWNMIX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAC3_DOWNMIX structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

