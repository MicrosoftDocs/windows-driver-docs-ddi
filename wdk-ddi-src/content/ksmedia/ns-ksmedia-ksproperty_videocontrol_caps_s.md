---
UID: NS:ksmedia.KSPROPERTY_VIDEOCONTROL_CAPS_S
title: KSPROPERTY_VIDEOCONTROL_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOCONTROL_CAPS_S structure describes the video-control capabilities of a minidriver, such as image flipping or event triggering abilities.
old-location: stream\ksproperty_videocontrol_caps_s.htm
old-project: stream
ms.assetid: e651202a-d0da-4147-9439-6cf0731c4886
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_VIDEOCONTROL_CAPS_S, KSPROPERTY_VIDEOCONTROL_CAPS_S, KSPROPERTY_VIDEOCONTROL_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCONTROL_CAPS_S, PKSPROPERTY_VIDEOCONTROL_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCONTROL_CAPS_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_CAPS_S, stream.ksproperty_videocontrol_caps_s, vidcapstruct_5b6a48da-ae8f-488c-8c9d-73de960df710.xml"
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
-	KSPROPERTY_VIDEOCONTROL_CAPS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCONTROL_CAPS_S, *PKSPROPERTY_VIDEOCONTROL_CAPS_S
---

# KSPROPERTY_VIDEOCONTROL_CAPS_S structure


## -description


The KSPROPERTY_VIDEOCONTROL_CAPS_S structure describes the video-control capabilities of a minidriver, such as image flipping or event triggering abilities.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      StreamIndex;
  ULONG      VideoControlCaps;
} KSPROPERTY_VIDEOCONTROL_CAPS_S, *PKSPROPERTY_VIDEOCONTROL_CAPS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field StreamIndex

Contains the zero-based index of the stream.


### -field VideoControlCaps

Indicates the video control capabilities for the specified stream. This member must be set to one or more (logically ORed) values from the <a href="..\ksmedia\ne-ksmedia-ks_videocontrolflags.md">KS_VideoControlFlags</a> enumeration.


## -see-also

<a href="..\ksmedia\ne-ksmedia-ks_videocontrolflags.md">KS_VideoControlFlags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568120">PROPSETID_VIDCAP_VIDEOCONTROL</a>



<a href="..\ksmedia\ns-ksmedia-ksproperty_videocontrol_mode_s.md">KSPROPERTY_VIDEOCONTROL_MODE_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566035">KSPROPERTY_VIDEOCONTROL_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEOCONTROL_CAPS_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

