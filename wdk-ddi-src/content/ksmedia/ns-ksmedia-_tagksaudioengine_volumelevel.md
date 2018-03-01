---
UID: NS:ksmedia._tagKSAUDIOENGINE_VOLUMELEVEL
title: "_tagKSAUDIOENGINE_VOLUMELEVEL"
author: windows-driver-content
description: The KSAUDIOENGINE_VOLUMELEVEL structure specifies the target volume level, ramp type, and duration within which the volume level should change, for a given volume level request via the KSPROPERTY_AUDIOENGINE_VOLUMELEVEL property.
old-location: audio\ksaudioengine_volumelevel.htm
old-project: audio
ms.assetid: E29E6F8B-F708-493B-94C3-A9DEE691ED3C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PKSAUDIOENGINE_VOLUMELEVEL, KSAUDIOENGINE_VOLUMELEVEL, KSAUDIOENGINE_VOLUMELEVEL structure [Audio Devices], PKSAUDIOENGINE_VOLUMELEVEL, PKSAUDIOENGINE_VOLUMELEVEL structure pointer [Audio Devices], _tagKSAUDIOENGINE_VOLUMELEVEL, audio.ksaudioengine_volumelevel, ksmedia/KSAUDIOENGINE_VOLUMELEVEL, ksmedia/PKSAUDIOENGINE_VOLUMELEVEL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KSAUDIOENGINE_VOLUMELEVEL
product: Windows
targetos: Windows
req.typenames: KSAUDIOENGINE_VOLUMELEVEL, *PKSAUDIOENGINE_VOLUMELEVEL
---

# _tagKSAUDIOENGINE_VOLUMELEVEL structure


## -description


The <b>KSAUDIOENGINE_VOLUMELEVEL</b> structure specifies the target volume level, ramp type, and duration within which the volume level should change, for a given volume level request via the <a href="https://msdn.microsoft.com/library/windows/hardware/hh831855">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a> property.


## -syntax


````
typedef struct _KSAUDIOENGINE_VOLUMELEVEL {
  LONG             TargetVolume;
  AUDIO_CURVE_TYPE CurveType;
  ULONGLONG        CurveDuration;
} KSAUDIOENGINE_VOLUMELEVEL, *PKSAUDIOENGINE_VOLUMELEVEL;
````


## -struct-fields




### -field TargetVolume

Specifies the desired final volume level using the scale defined for the <b>KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</b> property.


### -field CurveType

Uses the <a href="..\ksmedia\ne-ksmedia-audio_curve_type.md">AUDIO_CURVE_TYPE</a> enumeration to specify the curve algorithm to apply over the duration specified, in order to reach the desired level.  The curve begins at the current volume level and ends at the target volume level specified in the <b>TargetVolume</b> parameter.


### -field CurveDuration

Specifies the duration, in hundreds of nanoseconds, over which the volume curve must take effect.


## -see-also

<a href="..\ksmedia\ne-ksmedia-audio_curve_type.md">AUDIO_CURVE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831855">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIOENGINE_VOLUMELEVEL structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

