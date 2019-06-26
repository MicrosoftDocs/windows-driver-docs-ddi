---
UID: NS:ksmedia.__unnamed_struct_102
title: KSPROPERTY_TUNER_STANDARD_MODE_S (ksmedia.h)
description: The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.
old-location: stream\ksproperty_tuner_standard_mode_s.htm
tech.root: stream
ms.assetid: 5f725332-155d-484f-8eaf-b45e0d7413e7
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_STANDARD_MODE_S, PKSPROPERTY_TUNER_STANDARD_MODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_STANDARD_MODE_S, ksmedia/PKSPROPERTY_TUNER_STANDARD_MODE_S, stream.ksproperty_tuner_standard_mode_s, vidcapstruct_5b923a0a-26a2-4ef4-82d7-de7b3c3b67d0.xml"
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
- KSPROPERTY_TUNER_STANDARD_MODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_STANDARD_MODE_S, *PKSPROPERTY_TUNER_STANDARD_MODE_S
---

# KSPROPERTY_TUNER_STANDARD_MODE_S structure


## -description


The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field AutoDetect

A Boolean value that indicates whether the tuning device can automatically detect the tuner standard from the signal. <b>TRUE</b> indicates that the tuning device can automatically detect the tuner standard from the signal. <b>FALSE</b> indicates that the tuning device cannot automatically detect the tuner standard. 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-standard-mode">KSPROPERTY_TUNER_STANDARD_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>
 

 

