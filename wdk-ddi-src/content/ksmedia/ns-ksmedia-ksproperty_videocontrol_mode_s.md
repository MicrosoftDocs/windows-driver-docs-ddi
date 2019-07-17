---
UID: NS:ksmedia.__unnamed_struct_151
title: KSPROPERTY_VIDEOCONTROL_MODE_S (ksmedia.h)
description: The KSPROPERTY_VIDEOCONTROL_MODE_S structure describes video-control modes for a stream, such as image flipping or event triggering abilities.
old-location: stream\ksproperty_videocontrol_mode_s.htm
tech.root: stream
ms.assetid: ba6ac5ef-4153-479f-a1a9-b71d1d80786c
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_VIDEOCONTROL_MODE_S, KSPROPERTY_VIDEOCONTROL_MODE_S, KSPROPERTY_VIDEOCONTROL_MODE_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCONTROL_MODE_S, PKSPROPERTY_VIDEOCONTROL_MODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCONTROL_MODE_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_MODE_S, stream.ksproperty_videocontrol_mode_s, vidcapstruct_35950052-3872-4155-842f-b8615aa68234.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSPROPERTY_VIDEOCONTROL_MODE_S"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_VIDEOCONTROL_MODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCONTROL_MODE_S, *PKSPROPERTY_VIDEOCONTROL_MODE_S
---

# KSPROPERTY_VIDEOCONTROL_MODE_S structure


## -description


The KSPROPERTY_VIDEOCONTROL_MODE_S structure describes video-control modes for a stream, such as image flipping or event triggering abilities.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field StreamIndex

Contains the zero-based index of the stream.


### -field Mode

Specifies the video control mode. For a Set request, this member contains the requested video control mode. For a Get request, the minidriver should return the current video control mode of the device. This member can be one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-ks_videocontrolflags">KS_VideoControlFlags</a> enumeration values.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksproperty_videocontrol_caps_s">KSPROPERTY_VIDEOCONTROL_CAPS_S</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocontrol-mode">KSPROPERTY_VIDEOCONTROL_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-ks_videocontrolflags">KS_VideoControlFlags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-videocontrol">PROPSETID_VIDCAP_VIDEOCONTROL</a>
 

 

