---
UID: NS:ksmedia.KSPROPERTY_TVAUDIO_S
title: KSPROPERTY_TVAUDIO_S
author: windows-driver-content
description: The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings.
old-location: stream\ksproperty_tvaudio_s.htm
old-project: stream
ms.assetid: a2e26798-322a-4057-8c29-3429711e36a4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/PKSPROPERTY_TVAUDIO_S, PKSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S, stream.ksproperty_tvaudio_s, ksmedia/KSPROPERTY_TVAUDIO_S, vidcapstruct_d9dd7c2c-ed79-4efa-ae11-07e069abda5c.xml, *PKSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S structure [Streaming Media Devices], PKSPROPERTY_TVAUDIO_S structure pointer [Streaming Media Devices]
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
-	KSPROPERTY_TVAUDIO_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S"
---

# KSPROPERTY_TVAUDIO_S structure


## -description


The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      Mode;
} KSPROPERTY_TVAUDIO_S, *PKSPROPERTY_TVAUDIO_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Mode

Specifies the mode of the TV audio device. For Get requests, the minidriver returns the current mode of the TV audio device. For Set requests, the minidriver sets the current mode of the TV audio device to the specified value. This member can be one or more (logically ORed) of the following values:

<table>
<tr>
<th>Mode</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_MONO

</td>
<td>
Indicates that the audio is in mono.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_STEREO

</td>
<td>
Indicates that the audio is in stereo.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_A

</td>
<td>
Indicates that the audio is in the primary language.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_B

</td>
<td>
Indicates that the audio is in the second language supported by the device.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_C

</td>
<td>
Indicates that the audio is in the third language supported by the device.

</td>
</tr>
</table>
 


## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567811">PROPSETID_VIDCAP_TVAUDIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565944">KSPROPERTY_TVAUDIO_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TVAUDIO_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

