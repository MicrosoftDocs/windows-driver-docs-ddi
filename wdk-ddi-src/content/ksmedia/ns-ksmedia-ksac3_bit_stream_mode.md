---
UID: NS:ksmedia.KSAC3_BIT_STREAM_MODE
title: KSAC3_BIT_STREAM_MODE
author: windows-driver-content
description: The KSAC3_BIT_STREAM_MODE structure specifies the bit-stream mode, which is the type of audio service that is encoded into an AC-3 stream.
old-location: audio\ksac3_bit_stream_mode.htm
old-project: audio
ms.assetid: 1395687d-643a-40b5-9ca9-bff34c0dd6d5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ksmedia/PKSAC3_BIT_STREAM_MODE, aud-prop_b90587bf-508c-4e01-83ec-6fd925433d17.xml, *PKSAC3_BIT_STREAM_MODE, KSAC3_BIT_STREAM_MODE structure [Audio Devices], PKSAC3_BIT_STREAM_MODE, ksmedia/KSAC3_BIT_STREAM_MODE, KSAC3_BIT_STREAM_MODE, audio.ksac3_bit_stream_mode, PKSAC3_BIT_STREAM_MODE structure pointer [Audio Devices]
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
-	KSAC3_BIT_STREAM_MODE
product: Windows
targetos: Windows
req.typenames: KSAC3_BIT_STREAM_MODE, *PKSAC3_BIT_STREAM_MODE
---

# KSAC3_BIT_STREAM_MODE structure


## -description


The KSAC3_BIT_STREAM_MODE structure specifies the bit-stream mode, which is the type of audio service that is encoded into an AC-3 stream.


## -syntax


````
typedef struct {
  LONG BitStreamMode;
} KSAC3_BIT_STREAM_MODE, *PKSAC3_BIT_STREAM_MODE;
````


## -struct-fields




### -field BitStreamMode

Specifies the bit-stream mode. The <b>BitStreamMode</b> member is set to a value in the range 0 to 7. Specify the value of this member as one of the following constants:
<table>
<tr>
<th>Constant name</th>
<th>Value</th>
</tr>
<tr>
<td>
KSAC3_SERVICE_MAIN_AUDIO

</td>
<td>
0

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_NO_DIALOG

</td>
<td>
1

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_VISUALLY_IMPAIRED

</td>
<td>
2

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_HEARING_IMPAIRED

</td>
<td>
3

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_DIALOG_ONLY

</td>
<td>
4

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_COMMENTARY

</td>
<td>
5

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_EMERGENCY_FLASH

</td>
<td>
6

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_VOICE_OVER

</td>
<td>
7

</td>
</tr>
</table> 

These constants correspond to the bit-stream modes that are defined in the AC-3 specification. For more information, see the following Remarks section.


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537212">KSPROPERTY_AC3_BIT_STREAM_MODE</a> property.

For more information about bit stream modes, see the AC-3 specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537212">KSPROPERTY_AC3_BIT_STREAM_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAC3_BIT_STREAM_MODE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

