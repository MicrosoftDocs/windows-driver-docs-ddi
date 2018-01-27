---
UID: NS:ksmedia.KSPROPERTY_CROSSBAR_CAPS_S
title: KSPROPERTY_CROSSBAR_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_CROSSBAR_CAPS_S structure describes the crossbar capabilities for a device.
old-location: stream\ksproperty_crossbar_caps_s.htm
old-project: stream
ms.assetid: 65c0b401-e437-485a-99bc-75ce5296ef34
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CROSSBAR_CAPS_S, stream.ksproperty_crossbar_caps_s, *PKSPROPERTY_CROSSBAR_CAPS_S, ksmedia/PKSPROPERTY_CROSSBAR_CAPS_S, PKSPROPERTY_CROSSBAR_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CROSSBAR_CAPS_S, PKSPROPERTY_CROSSBAR_CAPS_S, vidcapstruct_db0a7a6a-8f6f-45d8-9d05-c520c8396858.xml, KSPROPERTY_CROSSBAR_CAPS_S structure [Streaming Media Devices]
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
-	KSPROPERTY_CROSSBAR_CAPS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CROSSBAR_CAPS_S, *PKSPROPERTY_CROSSBAR_CAPS_S
---

# KSPROPERTY_CROSSBAR_CAPS_S structure


## -description


The KSPROPERTY_CROSSBAR_CAPS_S structure describes the crossbar capabilities for a device.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      NumberOfInputs;
  ULONG      NumberOfOutputs;
} KSPROPERTY_CROSSBAR_CAPS_S, *PKSPROPERTY_CROSSBAR_CAPS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field NumberOfInputs

Indicates the number of audio and video input pins on the crossbar.


### -field NumberOfOutputs

Indicates the number of audio and video output pins on the crossbar.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565118">KSPROPERTY_CROSSBAR_CAPS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567804">PROPSETID_VIDCAP_CROSSBAR</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CROSSBAR_CAPS_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

