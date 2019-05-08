---
UID: NS:ksmedia.__unnamed_struct_97
title: KSPROPERTY_TUNER_IF_MEDIUM_S (ksmedia.h)
description: The KSPROPERTY_TUNER_IF_MEDIUM_S structure returns the Medium GUID for the pin that is capable of supporting tuning to an intermediate frequency.
old-location: stream\ksproperty_tuner_if_medium_s.htm
tech.root: stream
ms.assetid: 19f79b01-1a3c-4695-96ec-2f7410f6b4aa
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_TUNER_IF_MEDIUM_S, KSPROPERTY_TUNER_IF_MEDIUM_S, KSPROPERTY_TUNER_IF_MEDIUM_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_IF_MEDIUM_S, PKSPROPERTY_TUNER_IF_MEDIUM_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_IF_MEDIUM_S, ksmedia/PKSPROPERTY_TUNER_IF_MEDIUM_S, stream.ksproperty_tuner_if_medium_s, vidcapstruct_8fb32d31-0264-49c3-b8de-3773e37441cc.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_TUNER_IF_MEDIUM_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_IF_MEDIUM_S, *PKSPROPERTY_TUNER_IF_MEDIUM_S
---

# KSPROPERTY_TUNER_IF_MEDIUM_S structure


## -description


The KSPROPERTY_TUNER_IF_MEDIUM_S structure returns the Medium GUID for the pin that is capable of supporting tuning to an intermediate frequency.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field IFMedium

Specifies the GUID for the pin that is capable of supporting an intermediate frequency. If no pin supports an intermediate frequency, the minidriver should return GUID_NULL. 


## -remarks



Support for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565842">KSPROPERTY_TUNER_IF_MEDIUM</a> property causes <i>Kstvtune.ax</i> to create an additional pin representing an MPEG-2 transport stream. A data packet sent on this pin in user mode consists only of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567691">KS_TVTUNER_CHANGE_INFO</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565842">KSPROPERTY_TUNER_IF_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
 

 

