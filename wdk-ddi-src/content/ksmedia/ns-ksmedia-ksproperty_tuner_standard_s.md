---
UID: NS:ksmedia.KSPROPERTY_TUNER_STANDARD_S
title: KSPROPERTY_TUNER_STANDARD_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM.
old-location: stream\ksproperty_tuner_standard_s.htm
old-project: stream
ms.assetid: 3eea8ee2-1ad5-4e00-b0c3-0710b58a2518
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSPROPERTY_TUNER_STANDARD_S, ksmedia/PKSPROPERTY_TUNER_STANDARD_S, vidcapstruct_b7568a5f-0825-495b-97ff-c8cee17ab8d3.xml, KSPROPERTY_TUNER_STANDARD_S, stream.ksproperty_tuner_standard_s, PKSPROPERTY_TUNER_STANDARD_S structure pointer [Streaming Media Devices], *PKSPROPERTY_TUNER_STANDARD_S, ksmedia/KSPROPERTY_TUNER_STANDARD_S, KSPROPERTY_TUNER_STANDARD_S structure [Streaming Media Devices]
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
-	KSPROPERTY_TUNER_STANDARD_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_STANDARD_S, *PKSPROPERTY_TUNER_STANDARD_S
---

# KSPROPERTY_TUNER_STANDARD_S structure


## -description


The KSPROPERTY_TUNER_STANDARD_S structure describe the standard of a TV tuner device, such as PAL, NTSC or SECAM.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      Standard;
} KSPROPERTY_TUNER_STANDARD_S, *PKSPROPERTY_TUNER_STANDARD_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Standard

Describes an analog video standard. This member may be set to one or more (logically ORed) values from the <a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a> enumeration.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565907">KSPROPERTY_TUNER_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>



<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



<a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_STANDARD_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

