---
UID: NS:ksmedia._KSAUDIOMODULE_PROPERTY
title: _KSAUDIOMODULE_PROPERTY (ksmedia.h)
description: The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of the audio modules.
old-location: audio\ksaudiomodule_property.htm
tech.root: audio
ms.assetid: 1DE3F065-6F8E-402F-87EF-F9582E31BFFE
ms.date: 05/08/2018
ms.keywords: "*PKSAUDIOMODULE_PROPERTY, KSAUDIOMODULE_PROPERTY, KSAUDIOMODULE_PROPERTY structure [Audio Devices], PKSAUDIOMODULE_PROPERTY, PKSAUDIOMODULE_PROPERTY structure pointer [Audio Devices], _KSAUDIOMODULE_PROPERTY, audio.ksaudiomodule_property, ksmedia/KSAUDIOMODULE_PROPERTY, ksmedia/PKSAUDIOMODULE_PROPERTY"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSAUDIOMODULE_PROPERTY"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
- KSAUDIOMODULE_PROPERTY
product:
- Windows
targetos: Windows
req.typenames: KSAUDIOMODULE_PROPERTY, *PKSAUDIOMODULE_PROPERTY
---

# _KSAUDIOMODULE_PROPERTY structure


## -description


The <b>KSAUDIOMODULE_DESCRIPTOR</b> structure describes the static, external  properties of the audio modules.


## -struct-fields




### -field Property

The KSPROPERTY of the audio module is defined as follows.


### -field ClassId

The ClassId of the audio module. The ClassId is an identifier that establishes what type of module this is. The value and mapping is established by the ISV and IHV.


### -field InstanceId

The InstanceId of the audio module.  The InstanceId is a unique identifier that distinguishes this instance of a module from another instance of an module. 


## -remarks



For more information about audio modules, see  <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audiomodule-descriptors">KSPROPERTY_AUDIOMODULE_DESCRIPTORS</a>
 

 

