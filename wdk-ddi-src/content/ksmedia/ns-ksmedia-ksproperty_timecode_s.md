---
UID: NS:ksmedia.KSPROPERTY_TIMECODE_S
title: KSPROPERTY_TIMECODE_S
author: windows-driver-content
description: The KSPROPERTY_TIMECODE_S structure describes a timecode.
old-location: stream\ksproperty_timecode_s.htm
old-project: stream
ms.assetid: 45af16ee-7405-44a4-ad14-e2cf9d916164
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSPROPERTY_TIMECODE_S, KSPROPERTY_TIMECODE_S structure [Streaming Media Devices], ksmedia/KSPROPERTY_TIMECODE_S, PKSPROPERTY_TIMECODE_S structure pointer [Streaming Media Devices], stream.ksproperty_timecode_s, vidcapstruct_03a0e9f7-37b7-4591-8cbc-e1d189c82ef2.xml, PKSPROPERTY_TIMECODE_S, ksmedia/PKSPROPERTY_TIMECODE_S, KSPROPERTY_TIMECODE_S"
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
-	KSPROPERTY_TIMECODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TIMECODE_S, *PKSPROPERTY_TIMECODE_S
---

# KSPROPERTY_TIMECODE_S structure


## -description


The KSPROPERTY_TIMECODE_S structure describes a timecode.


## -syntax


````
typedef struct {
  KSPROPERTY      Property;
  TIMECODE_SAMPLE TimecodeSamp;
} KSPROPERTY_TIMECODE_S, *PKSPROPERTY_TIMECODE_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field TimecodeSamp

Specifies the timecode sample. Timecode, absolute track number (ATN) and relative time counter (RTC) are in the <b>TimecodeSamp.timecode.dwFrames</b> member.


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_timecode_node_s.md">KSPROPERTY_TIMECODE_NODE_S</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ns-ksmedia-tagtimecode_sample.md">TIMECODE_SAMPLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TIMECODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

