---
UID: NS:ksmedia.KSPROPERTY_TVAUDIO_CAPS_S
title: KSPROPERTY_TVAUDIO_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_TVAUDIO_CAPS_S structure describes the capability of a TV audio device, such as stereo versus mono audio support and language capabilities.
old-location: stream\ksproperty_tvaudio_caps_s.htm
tech.root: stream
ms.assetid: 991208ee-d245-41d1-a5e6-0e79368e37a8
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_TVAUDIO_CAPS_S, KSPROPERTY_TVAUDIO_CAPS_S, KSPROPERTY_TVAUDIO_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TVAUDIO_CAPS_S, PKSPROPERTY_TVAUDIO_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TVAUDIO_CAPS_S, ksmedia/PKSPROPERTY_TVAUDIO_CAPS_S, stream.ksproperty_tvaudio_caps_s, vidcapstruct_dd4243d2-9778-4dae-99e2-0d32a73ab0d4.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSPROPERTY_TVAUDIO_CAPS_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TVAUDIO_CAPS_S, *PKSPROPERTY_TVAUDIO_CAPS_S
---

# KSPROPERTY_TVAUDIO_CAPS_S structure


## -description


The KSPROPERTY_TVAUDIO_CAPS_S structure describes the capability of a TV audio device, such as stereo versus mono audio support and language capabilities.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Capabilities

Specifies the capabilities of the TV audio device. The minidriver returns the capabilities of the TV audio device by setting this member to one or more (logically ORed) values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_MONO

</td>
<td>
Indicates the device supports mono audio.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_STEREO

</td>
<td>
Indicates the device supports stereo audio.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_A

</td>
<td>
Indicates the device supports a primary (default) language.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_B

</td>
<td>
Indicates the device supports a second language.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_C

</td>
<td>
Indicates the device supports a third language.

</td>
</tr>
</table>
 


### -field InputMedium

Reserved for system use.


### -field OutputMedium

Reserved for system use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565933">KSPROPERTY_TVAUDIO_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567811">PROPSETID_VIDCAP_TVAUDIO</a>
 

 

