---
UID: NS:ksmedia.SYSAUDIO_ATTACH_VIRTUAL_SOURCE
title: SYSAUDIO_ATTACH_VIRTUAL_SOURCE
author: windows-driver-content
description: The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device.
old-location: audio\sysaudio_attach_virtual_source.htm
old-project: audio
ms.assetid: 1215cf8e-8e94-4da4-9fb9-2212e8386abd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SYSAUDIO_ATTACH_VIRTUAL_SOURCE, *PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, SYSAUDIO_ATTACH_VIRTUAL_SOURCE
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
req.alt-api: SYSAUDIO_ATTACH_VIRTUAL_SOURCE
req.alt-loc: ksmedia.h
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
req.typenames: *PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, SYSAUDIO_ATTACH_VIRTUAL_SOURCE
---

# SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure



## -description
The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device.



## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      MixerPinId;
  ULONG      Reserved;
} SYSAUDIO_ATTACH_VIRTUAL_SOURCE, *PSYSAUDIO_ATTACH_VIRTUAL_SOURCE;
````


## -struct-fields

### -field Property

Specifies the property. This parameter is a structure of type <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>.


### -field MixerPinId

Specifies the virtual source index.


### -field Reserved

Reserved. Set to zero.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537413">KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE</a> property.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537413">KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

