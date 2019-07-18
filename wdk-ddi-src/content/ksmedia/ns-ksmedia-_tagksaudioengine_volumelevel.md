---
UID: NS:ksmedia._tagKSAUDIOENGINE_VOLUMELEVEL
title: _tagKSAUDIOENGINE_VOLUMELEVEL (ksmedia.h)
description: The KSAUDIOENGINE_VOLUMELEVEL structure specifies the target volume level, ramp type, and duration within which the volume level should change, for a given volume level request via the KSPROPERTY_AUDIOENGINE_VOLUMELEVEL property.
old-location: audio\ksaudioengine_volumelevel.htm
tech.root: audio
ms.assetid: E29E6F8B-F708-493B-94C3-A9DEE691ED3C
ms.date: 05/08/2018
ms.keywords: "*PKSAUDIOENGINE_VOLUMELEVEL, KSAUDIOENGINE_VOLUMELEVEL, KSAUDIOENGINE_VOLUMELEVEL structure [Audio Devices], PKSAUDIOENGINE_VOLUMELEVEL, PKSAUDIOENGINE_VOLUMELEVEL structure pointer [Audio Devices], _tagKSAUDIOENGINE_VOLUMELEVEL, audio.ksaudioengine_volumelevel, ksmedia/KSAUDIOENGINE_VOLUMELEVEL, ksmedia/PKSAUDIOENGINE_VOLUMELEVEL"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSAUDIOENGINE_VOLUMELEVEL"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
- Ksmedia.h
api_name:
- KSAUDIOENGINE_VOLUMELEVEL
product:
- Windows
targetos: Windows
req.typenames: KSAUDIOENGINE_VOLUMELEVEL, *PKSAUDIOENGINE_VOLUMELEVEL
---

# _tagKSAUDIOENGINE_VOLUMELEVEL structure


## -description


The <b>KSAUDIOENGINE_VOLUMELEVEL</b> structure specifies the target volume level, ramp type, and duration within which the volume level should change, for a given volume level request via the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audioengine-volumelevel">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a> property.


## -struct-fields




### -field TargetVolume

Specifies the desired final volume level using the scale defined for the <b>KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</b> property.


### -field CurveType

Uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-audio_curve_type">AUDIO_CURVE_TYPE</a> enumeration to specify the curve algorithm to apply over the duration specified, in order to reach the desired level.  The curve begins at the current volume level and ends at the target volume level specified in the <b>TargetVolume</b> parameter.


### -field CurveDuration

Specifies the duration, in hundreds of nanoseconds, over which the volume curve must take effect.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-audio_curve_type">AUDIO_CURVE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audioengine-volumelevel">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a>
 

 

