---
UID: NS:ksmedia._KSAUDIOMODULE_PROPERTY
title: "_KSAUDIOMODULE_PROPERTY"
author: windows-driver-content
description: The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of the audio modules.
old-location: audio\ksaudiomodule_property.htm
old-project: audio
ms.assetid: 1DE3F065-6F8E-402F-87EF-F9582E31BFFE
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSAUDIOMODULE_PROPERTY, KSAUDIOMODULE_PROPERTY, KSAUDIOMODULE_PROPERTY structure [Audio Devices], PKSAUDIOMODULE_PROPERTY, PKSAUDIOMODULE_PROPERTY structure pointer [Audio Devices], _KSAUDIOMODULE_PROPERTY, audio.ksaudiomodule_property, ksmedia/KSAUDIOMODULE_PROPERTY, ksmedia/PKSAUDIOMODULE_PROPERTY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KSAUDIOMODULE_PROPERTY
product: Windows
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



For more information about audio modules, see  <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 




## -see-also




<a href="https://msdn.microsoft.com/EAD613AA-005B-4751-B60E-212853CA40B4">KSPROPERTY_AUDIOMODULE_DESCRIPTORS</a>
 

 

