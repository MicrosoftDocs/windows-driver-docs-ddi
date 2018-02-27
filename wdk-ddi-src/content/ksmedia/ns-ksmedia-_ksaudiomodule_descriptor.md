---
UID: NS:ksmedia._KSAUDIOMODULE_DESCRIPTOR
title: "_KSAUDIOMODULE_DESCRIPTOR"
author: windows-driver-content
description: The KSAUDIOMODULE_DESCRIPTOR structure describes the static, external properties of audio modules.
old-location: audio\ksaudiomodule_descriptor.htm
old-project: audio
ms.assetid: 3A991D49-B873-4C03-8A5B-D91EB5E63192
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PKSAUDIOMODULE_DESCRIPTOR, KSAUDIOMODULE_DESCRIPTOR, KSAUDIOMODULE_DESCRIPTOR structure [Audio Devices], PKSAUDIOMODULE_DESCRIPTOR, PKSAUDIOMODULE_DESCRIPTOR structure pointer [Audio Devices], _KSAUDIOMODULE_DESCRIPTOR, audio.ksaudiomodule_descriptor, ksmedia/KSAUDIOMODULE_DESCRIPTOR, ksmedia/PKSAUDIOMODULE_DESCRIPTOR"
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
-	KSAUDIOMODULE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: KSAUDIOMODULE_DESCRIPTOR, *PKSAUDIOMODULE_DESCRIPTOR
---

# _KSAUDIOMODULE_DESCRIPTOR structure


## -description


The <b>KSAUDIOMODULE_DESCRIPTOR</b> structure describes the static, external  properties of audio modules.


## -syntax


````
typedef struct _KSAUDIOMODULE_DESCRIPTOR {
  GUID  ClassId;
  ULONG InstanceId;
  ULONG VersionMajor;
  ULONG VersionMinor;
  WCHAR Name[AUDIOMODULE_MAX_NAME_CCH_SIZE];
} KSAUDIOMODULE_DESCRIPTOR, *PKSAUDIOMODULE_DESCRIPTOR;
````


## -struct-fields




### -field ClassId

The ClassId of the audio module. The ClassId is an identifier that establishes what type of module this is. The value and mapping is established by the ISV and IHV.


### -field InstanceId

The InstanceId of the audio module.  The InstanceId is a unique identifier that distinguishes this instance of a module from another instance of a module. 


### -field VersionMajor

The major version of the audio module. Usage is defined by the implementer.


### -field VersionMinor

The minor version of the audio module.  Usage is defined by the implementer.


### -field Name

 




#### - Name[AUDIOMODULE_MAX_NAME_CCH_SIZE]

The friendly name of the audio module. The maximum length is AUDIOMODULE_MAX_NAME_CCH_SIZE wide characters. It is defined as 128 in KSMedia.h.


## -remarks



For more information about audio modules, see  <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 




## -see-also

<a href="https://msdn.microsoft.com/EAD613AA-005B-4751-B60E-212853CA40B4">KSPROPERTY_AUDIOMODULE_DESCRIPTORS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIOMODULE_DESCRIPTOR structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

