---
UID: NS:ksmedia.__unnamed_struct_98
title: KSPROPERTY_TUNER_FREQUENCY_S (ksmedia.h)
description: The KSPROPERTY_TUNER_FREQUENCY_S structure describes the frequency of a TV or radio tuner device.
old-location: stream\ksproperty_tuner_frequency_s.htm
tech.root: stream
ms.assetid: 19d2c3cc-69e3-4216-9eb7-32b522fe058b
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_TUNER_FREQUENCY_S, KSPROPERTY_TUNER_FREQUENCY_S, KSPROPERTY_TUNER_FREQUENCY_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_FREQUENCY_S, PKSPROPERTY_TUNER_FREQUENCY_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_FREQUENCY_S, ksmedia/PKSPROPERTY_TUNER_FREQUENCY_S, stream.ksproperty_tuner_frequency_s, vidcapstruct_7757eed6-a41b-4bcd-ad7b-05aca3b54cd0.xml"
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
-	KSPROPERTY_TUNER_FREQUENCY_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_FREQUENCY_S, *PKSPROPERTY_TUNER_FREQUENCY_S
---

# KSPROPERTY_TUNER_FREQUENCY_S structure


## -description


The KSPROPERTY_TUNER_FREQUENCY_S structure describes the frequency of a TV or radio tuner device.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Frequency

Specifies the frequency of the tuner. If the request is a Get request, the minidriver returns the current frequency of the tuner. If the request is a Set request, the minidriver should set the frequency of the tuner to the specified value. This value is specified in hertz (Hz).


### -field LastFrequency

Specifies the last frequency tuned.


### -field TuningFlags

Specifies tuning flags that describe the granularity of a tuning operation. If the request is a Get request, the minidriver returns the current tuning flags. If the request is a Set request, the minidriver should use the specified tuning method. This member must be set to one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567689">KS_TUNER_TUNING_FLAGS</a> enumeration.


### -field VideoSubChannel

Specifies the video subchannel of a digital television source. If the request is a Get request, the minidriver should return the video subchannel for the digital television source to the specified value. If the request is a Set request, the minidriver should set the video subchannel for the digital television source. This member is only used by devices that support the DSS tuner mode (KSPROPERTY_TUNER_MODE_DSS).


### -field AudioSubChannel

Specifies the audio subchannel of a digital television source. If the request is a Get request, the minidriver should return the audio subchannel for the digital television source. If the request is a Set request, the minidriver should set the audio subchannel for the digital television source. This member is only used by devices that support the DSS tuner mode (KSPROPERTY_TUNER_MODE_DSS).


### -field Channel

Specifies the video subchannel of a digital television source. If the request is a Get request, the minidriver should return the video subchannel for the digital television source to the specified value. If the request is a Set request, the minidriver should set the video subchannel for the digital television source. This member is only used by devices that support the DSS tuner mode (KSPROPERTY_TUNER_MODE_DSS).


### -field Country

Specifies the current country code for the tuning operation. Country codes follow the Telephony API (TAPI) region code values that correspond to the international long distance dialing codes. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565833">KSPROPERTY_TUNER_FREQUENCY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567689">KS_TUNER_TUNING_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
 

 

