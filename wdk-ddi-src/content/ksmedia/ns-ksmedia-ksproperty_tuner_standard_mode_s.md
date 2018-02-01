---
UID: NS:ksmedia.KSPROPERTY_TUNER_STANDARD_MODE_S
title: KSPROPERTY_TUNER_STANDARD_MODE_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.
old-location: stream\ksproperty_tuner_standard_mode_s.htm
old-project: stream
ms.assetid: 5f725332-155d-484f-8eaf-b45e0d7413e7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KSPROPERTY_TUNER_STANDARD_MODE_S, stream.ksproperty_tuner_standard_mode_s, vidcapstruct_5b923a0a-26a2-4ef4-82d7-de7b3c3b67d0.xml, ksmedia/PKSPROPERTY_TUNER_STANDARD_MODE_S, PKSPROPERTY_TUNER_STANDARD_MODE_S, *PKSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_STANDARD_MODE_S structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
-	KSPROPERTY_TUNER_STANDARD_MODE_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S"
---

# KSPROPERTY_TUNER_STANDARD_MODE_S structure


## -description


The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  BOOL       AutoDetect;
} KSPROPERTY_TUNER_STANDARD_MODE_S, *PKSPROPERTY_TUNER_STANDARD_MODE_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field AutoDetect

A Boolean value that indicates whether the tuning device can automatically detect the tuner standard from the signal. <b>TRUE</b> indicates that the tuning device can automatically detect the tuner standard from the signal. <b>FALSE</b> indicates that the tuning device cannot automatically detect the tuner standard. 


## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565909">KSPROPERTY_TUNER_STANDARD_MODE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_STANDARD_MODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

