---
UID: NS:ksmedia.SYSAUDIO_CREATE_VIRTUAL_SOURCE
title: SYSAUDIO_CREATE_VIRTUAL_SOURCE
author: windows-driver-content
description: The SYSAUDIO_CREATE_VIRTUAL_SOURCE structure is used to create a mixer-line virtual source such as a volume control or mute.
old-location: audio\sysaudio_create_virtual_source.htm
old-project: audio
ms.assetid: c9024cf0-aa0c-4652-89c1-3f2e6f622b3d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SYSAUDIO_CREATE_VIRTUAL_SOURCE structure [Audio Devices], PSYSAUDIO_CREATE_VIRTUAL_SOURCE, ksmedia/PSYSAUDIO_CREATE_VIRTUAL_SOURCE, aud-prop_b5e1f1ed-6007-4f2a-89eb-dcabeb0777e6.xml, *PSYSAUDIO_CREATE_VIRTUAL_SOURCE, SYSAUDIO_CREATE_VIRTUAL_SOURCE, PSYSAUDIO_CREATE_VIRTUAL_SOURCE structure pointer [Audio Devices], audio.sysaudio_create_virtual_source, ksmedia/SYSAUDIO_CREATE_VIRTUAL_SOURCE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
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

Specifies the property. This parameter is a structure of type <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>.


### -field PinCategory

Specifies a category for the created pin. This parameter is a KSCATEGORY_<i>Xxx</i> GUID.


### -field PinName

Specifies a name for the created pin. If the <i>PinCategory</i> parameter uniquely identifies the pin to create, set <i>PinName</i> to the same GUID as <i>PinCategory</i>. Otherwise, set <i>PinName</i> to a pin-name GUID that uniquely distinguishes the target pin from other pins of type KSCATEGORY_<i>Xxx</i>.


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537417">KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE</a> property.



## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537417">KSPROPERTY_SYSAUDIO_CREATE_VIRTUAL_SOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SYSAUDIO_CREATE_VIRTUAL_SOURCE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

