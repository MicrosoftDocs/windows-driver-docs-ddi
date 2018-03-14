---
UID: NS:ksmedia.SYSAUDIO_CREATE_VIRTUAL_SOURCE
title: SYSAUDIO_CREATE_VIRTUAL_SOURCE
author: windows-driver-content
description: The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute.
old-location: audio\sysaudio_create_virtual_source.htm
old-project: audio
ms.assetid: c9024cf0-aa0c-4652-89c1-3f2e6f622b3d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PSYSAUDIO_CREATE_VIRTUAL_SOURCE, PSYSAUDIO_CREATE_VIRTUAL_SOURCE, PSYSAUDIO_CREATE_VIRTUAL_SOURCE structure pointer [Audio Devices], SYSAUDIO_CREATE_VIRTUAL_SOURCE, SYSAUDIO_CREATE_VIRTUAL_SOURCE structure [Audio Devices], aud-prop_b5e1f1ed-6007-4f2a-89eb-dcabeb0777e6.xml, audio.sysaudio_create_virtual_source, ksmedia/PSYSAUDIO_CREATE_VIRTUAL_SOURCE, ksmedia/SYSAUDIO_CREATE_VIRTUAL_SOURCE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	SYSAUDIO_CREATE_VIRTUAL_SOURCE
product: Windows
targetos: Windows
req.typenames: SYSAUDIO_CREATE_VIRTUAL_SOURCE, *PSYSAUDIO_CREATE_VIRTUAL_SOURCE
---

# SYSAUDIO_CREATE_VIRTUAL_SOURCE structure


## -description


The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  GUID       PinCategory;
  GUID       PinName;
} SYSAUDIO_CREATE_VIRTUAL_SOURCE, *PSYSAUDIO_CREATE_VIRTUAL_SOURCE;
````


## -struct-fields




### -field Property

Specifies the property. This parameter is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.


### -field PinCategory

Specifies a category for the created pin. This parameter is a KSCATEGORY_<i>Xxx</i> GUID.


### -field PinName

Specifies a name for the created pin. If the <i>PinCategory</i> parameter uniquely identifies the pin to create, set <i>PinName</i> to the same GUID as <i>PinCategory</i>. Otherwise, set <i>PinName</i> to a pin-name GUID that uniquely distinguishes the target pin from other pins of type KSCATEGORY_<i>Xxx</i>.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537417">KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE</a> property.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537417">KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE</a>



 

 


