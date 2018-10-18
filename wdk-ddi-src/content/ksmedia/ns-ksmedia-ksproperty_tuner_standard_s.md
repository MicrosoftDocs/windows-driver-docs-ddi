---
UID: NS:ksmedia.KSPROPERTY_TUNER_STANDARD_S
title: KSPROPERTY_TUNER_STANDARD_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM.
old-location: stream\ksproperty_tuner_standard_s.htm
tech.root: stream
ms.assetid: 3eea8ee2-1ad5-4e00-b0c3-0710b58a2518
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_TUNER_STANDARD_S, KSPROPERTY_TUNER_STANDARD_S, KSPROPERTY_TUNER_STANDARD_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_STANDARD_S, PKSPROPERTY_TUNER_STANDARD_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_STANDARD_S, ksmedia/PKSPROPERTY_TUNER_STANDARD_S, stream.ksproperty_tuner_standard_s, vidcapstruct_b7568a5f-0825-495b-97ff-c8cee17ab8d3.xml"
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
-	KSPROPERTY_TUNER_STANDARD_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_STANDARD_S, *PKSPROPERTY_TUNER_STANDARD_S
---

# KSPROPERTY_TUNER_STANDARD_S structure


## -description


The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Standard

Describes an analog video standard. This member may be set to one or more (logically ORed) values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567297">KS_AnalogVideoStandard</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565907">KSPROPERTY_TUNER_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567297">KS_AnalogVideoStandard</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
 

 

