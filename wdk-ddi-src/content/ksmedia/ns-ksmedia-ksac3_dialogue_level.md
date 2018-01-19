---
UID: NS:ksmedia.KSAC3_DIALOGUE_LEVEL
title: KSAC3_DIALOGUE_LEVEL
author: windows-driver-content
description: The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream.
old-location: audio\ksac3_dialogue_level.htm
old-project: audio
ms.assetid: c29d5cbc-ddcc-42e9-ac2d-e442a489adfd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSAC3_DIALOGUE_LEVEL, KSAC3_DIALOGUE_LEVEL, *PKSAC3_DIALOGUE_LEVEL
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
req.alt-api: KSAC3_DIALOGUE_LEVEL
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
req.typenames: KSAC3_DIALOGUE_LEVEL, *PKSAC3_DIALOGUE_LEVEL
---

# KSAC3_DIALOGUE_LEVEL structure



## -description
The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream.



## -syntax

````
typedef struct {
  ULONG DialogueLevel;
} KSAC3_DIALOGUE_LEVEL, *PKSAC3_DIALOGUE_LEVEL;
````


## -struct-fields

### -field DialogueLevel

Specifies how far the average dialog level is below digital 100 percent. Valid values are 1 through 31. The values 1 through 31 are interpreted as -1 decibels through -31 decibels with respect to digital 100 percent.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537212">KSPROPERTY_AC3_BIT_STREAM_MODE</a> property.

For more information about dialog levels, see the AC-3 specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537212">KSPROPERTY_AC3_BIT_STREAM_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAC3_DIALOGUE_LEVEL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

