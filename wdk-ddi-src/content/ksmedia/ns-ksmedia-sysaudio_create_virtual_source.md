---
UID: NS:ksmedia.__unnamed_struct_57
title: SYSAUDIO_CREATE_VIRTUAL_SOURCE (ksmedia.h)
description: The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute.
old-location: audio\sysaudio_create_virtual_source.htm
tech.root: audio
ms.assetid: c9024cf0-aa0c-4652-89c1-3f2e6f622b3d
ms.date: 04/30/2019
keywords: ["SYSAUDIO_CREATE_VIRTUAL_SOURCE structure"]
ms.keywords: "*PSYSAUDIO_CREATE_VIRTUAL_SOURCE, PSYSAUDIO_CREATE_VIRTUAL_SOURCE, PSYSAUDIO_CREATE_VIRTUAL_SOURCE structure pointer [Audio Devices], SYSAUDIO_CREATE_VIRTUAL_SOURCE, SYSAUDIO_CREATE_VIRTUAL_SOURCE structure [Audio Devices], aud-prop_b5e1f1ed-6007-4f2a-89eb-dcabeb0777e6.xml, audio.sysaudio_create_virtual_source, ksmedia/PSYSAUDIO_CREATE_VIRTUAL_SOURCE, ksmedia/SYSAUDIO_CREATE_VIRTUAL_SOURCE"
f1_keywords:
 - "ksmedia/SYSAUDIO_CREATE_VIRTUAL_SOURCE"
 - "SYSAUDIO_CREATE_VIRTUAL_SOURCE"
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
- SYSAUDIO_CREATE_VIRTUAL_SOURCE
targetos: Windows
req.typenames: SYSAUDIO_CREATE_VIRTUAL_SOURCE, *PSYSAUDIO_CREATE_VIRTUAL_SOURCE
---

# SYSAUDIO_CREATE_VIRTUAL_SOURCE structure


## -description


The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute.


## -struct-fields




### -field Property

Specifies the property. This parameter is a structure of type <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.


### -field PinCategory

Specifies a category for the created pin. This parameter is a KSCATEGORY_<i>Xxx</i> GUID.


### -field PinName

Specifies a name for the created pin. If the <i>PinCategory</i> parameter uniquely identifies the pin to create, set <i>PinName</i> to the same GUID as <i>PinCategory</i>. Otherwise, set <i>PinName</i> to a pin-name GUID that uniquely distinguishes the target pin from other pins of type KSCATEGORY_<i>Xxx</i>.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-sysaudio-create-virtual-source">KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE</a> property.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-sysaudio-create-virtual-source">KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE</a>
 

 

