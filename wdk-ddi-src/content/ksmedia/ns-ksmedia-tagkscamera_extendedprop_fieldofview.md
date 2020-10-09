---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
title: tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW (ksmedia.h)
description: The Field of View Control property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position.
old-location: stream\kscamera_extendedprop_fieldofview.htm
tech.root: stream
ms.assetid: CC3FFC63-8404-4EA6-9738-F0A3C52585B8
ms.date: 04/23/2018
keywords: ["tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure"]
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, KSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, ksmedia/PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, stream.kscamera_extendedprop_fieldofview, tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.typenames: KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, *PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
 - PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
 - ksmedia/PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
 - KSCAMERA_EXTENDEDPROP_FIELDOFVIEW
 - ksmedia/KSCAMERA_EXTENDEDPROP_FIELDOFVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KSCAMERA_EXTENDEDPROP_FIELDOFVIEW
---

# tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure


## -description

The <i>Field of View Control</i> property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position.

## -struct-fields

### -field NormalizedFocalLengthX

The horizontal focal length, in millimeters, normalized to a 35mm camera aperture size.

### -field NormalizedFocalLengthY

The vertical focal length, in millimeters, normalized to a 35mm camera aperture size.

### -field Flag

Reserved. Set to 0.

### -field Reserved

Reserved. Set to 0.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-fieldofview">KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW</a>