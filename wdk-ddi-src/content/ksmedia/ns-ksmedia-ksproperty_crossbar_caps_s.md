---
UID: NS:ksmedia.__unnamed_struct_140
title: KSPROPERTY_CROSSBAR_CAPS_S (ksmedia.h)
description: The KSPROPERTY_CROSSBAR_CAPS_S structure describes the crossbar capabilities for a device.
old-location: stream\ksproperty_crossbar_caps_s.htm
tech.root: stream
ms.assetid: 65c0b401-e437-485a-99bc-75ce5296ef34
ms.date: 04/30/2019
keywords: ["KSPROPERTY_CROSSBAR_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_CROSSBAR_CAPS_S, KSPROPERTY_CROSSBAR_CAPS_S, KSPROPERTY_CROSSBAR_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_CROSSBAR_CAPS_S, PKSPROPERTY_CROSSBAR_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CROSSBAR_CAPS_S, ksmedia/PKSPROPERTY_CROSSBAR_CAPS_S, stream.ksproperty_crossbar_caps_s, vidcapstruct_db0a7a6a-8f6f-45d8-9d05-c520c8396858.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_CROSSBAR_CAPS_S"
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
- KSPROPERTY_CROSSBAR_CAPS_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CROSSBAR_CAPS_S, *PKSPROPERTY_CROSSBAR_CAPS_S
---

# KSPROPERTY_CROSSBAR_CAPS_S structure


## -description


The KSPROPERTY_CROSSBAR_CAPS_S structure describes the crossbar capabilities for a device.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field NumberOfInputs

Indicates the number of audio and video input pins on the crossbar.


### -field NumberOfOutputs

Indicates the number of audio and video output pins on the crossbar.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-crossbar-caps">KSPROPERTY_CROSSBAR_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-crossbar">PROPSETID_VIDCAP_CROSSBAR</a>
 

 

