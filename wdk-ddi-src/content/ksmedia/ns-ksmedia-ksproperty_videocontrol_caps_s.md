---
UID: NS:ksmedia.KSPROPERTY_VIDEOCONTROL_CAPS_S
title: KSPROPERTY_VIDEOCONTROL_CAPS_S (ksmedia.h)
description: The KSPROPERTY_VIDEOCONTROL_CAPS_S structure describes the video-control capabilities of a minidriver, such as image flipping or event triggering abilities.
old-location: stream\ksproperty_videocontrol_caps_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_VIDEOCONTROL_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_VIDEOCONTROL_CAPS_S, KSPROPERTY_VIDEOCONTROL_CAPS_S, KSPROPERTY_VIDEOCONTROL_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCONTROL_CAPS_S, PKSPROPERTY_VIDEOCONTROL_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCONTROL_CAPS_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_CAPS_S, stream.ksproperty_videocontrol_caps_s, vidcapstruct_5b6a48da-ae8f-488c-8c9d-73de960df710.xml"
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
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCONTROL_CAPS_S, *PKSPROPERTY_VIDEOCONTROL_CAPS_S
f1_keywords:
 - PKSPROPERTY_VIDEOCONTROL_CAPS_S
 - ksmedia/PKSPROPERTY_VIDEOCONTROL_CAPS_S
 - KSPROPERTY_VIDEOCONTROL_CAPS_S
 - ksmedia/KSPROPERTY_VIDEOCONTROL_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_VIDEOCONTROL_CAPS_S
 - KSPROPERTY_VIDEOCONTROL_CAPS_S
---

# KSPROPERTY_VIDEOCONTROL_CAPS_S structure


## -description

The KSPROPERTY_VIDEOCONTROL_CAPS_S structure describes the video-control capabilities of a minidriver, such as image flipping or event triggering abilities.

## -struct-fields

### -field Property

Specifies an initialized <a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field StreamIndex

Contains the zero-based index of the stream.

### -field VideoControlCaps

Indicates the video control capabilities for the specified stream. This member must be set to one or more (logically ORed) values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_videocontrolflags">KS_VideoControlFlags</a> enumeration.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videocontrol-caps">KSPROPERTY_VIDEOCONTROL_CAPS</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_videocontrol_mode_s">KSPROPERTY_VIDEOCONTROL_MODE_S</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_videocontrolflags">KS_VideoControlFlags</a>



<a href="/windows-hardware/drivers/stream/propsetid-vidcap-videocontrol">PROPSETID_VIDCAP_VIDEOCONTROL</a>

