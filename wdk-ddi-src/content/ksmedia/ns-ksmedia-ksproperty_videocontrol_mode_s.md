---
UID: NS:ksmedia.KSPROPERTY_VIDEOCONTROL_MODE_S
title: KSPROPERTY_VIDEOCONTROL_MODE_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOCONTROL_MODE_S structure describes video-control modes for a stream, such as image flipping or event triggering abilities.
old-location: stream\ksproperty_videocontrol_mode_s.htm
old-project: stream
ms.assetid: ba6ac5ef-4153-479f-a1a9-b71d1d80786c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_VIDEOCONTROL_MODE_S, KSPROPERTY_VIDEOCONTROL_MODE_S, KSPROPERTY_VIDEOCONTROL_MODE_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCONTROL_MODE_S, PKSPROPERTY_VIDEOCONTROL_MODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCONTROL_MODE_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_MODE_S, stream.ksproperty_videocontrol_mode_s, vidcapstruct_35950052-3872-4155-842f-b8615aa68234.xml"
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
-	KSPROPERTY_VIDEOCONTROL_MODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCONTROL_MODE_S, *PKSPROPERTY_VIDEOCONTROL_MODE_S
---

# KSPROPERTY_VIDEOCONTROL_MODE_S structure


## -description


The KSPROPERTY_VIDEOCONTROL_MODE_S structure describes video-control modes for a stream, such as image flipping or event triggering abilities.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      StreamIndex;
  LONG       Mode;
} KSPROPERTY_VIDEOCONTROL_MODE_S, *PKSPROPERTY_VIDEOCONTROL_MODE_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field StreamIndex

Contains the zero-based index of the stream.


### -field Mode

Specifies the video control mode. For a Set request, this member contains the requested video control mode. For a Get request, the minidriver should return the current video control mode of the device. This member can be one of the <a href="..\ksmedia\ne-ksmedia-ks_videocontrolflags.md">KS_VideoControlFlags</a> enumeration values.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566042">KSPROPERTY_VIDEOCONTROL_MODE</a>



<a href="..\ksmedia\ne-ksmedia-ks_videocontrolflags.md">KS_VideoControlFlags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568120">PROPSETID_VIDCAP_VIDEOCONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="..\ksmedia\ns-ksmedia-ksproperty_videocontrol_caps_s.md">KSPROPERTY_VIDEOCONTROL_CAPS_S</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEOCONTROL_MODE_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

