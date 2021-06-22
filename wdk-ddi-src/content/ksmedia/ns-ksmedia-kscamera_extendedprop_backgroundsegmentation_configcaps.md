---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
tech.root: stream
title: KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
ms.date: 06/24/2021
targetos: Windows
description: The KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS structure is used to list which stream configurations support background segmentation.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS, *PKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - PKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - PKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - ksmedia/PKSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
 - ksmedia/KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS
dev_langs:
 - c++
---

## -description

The **KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_CONFIGCAPS** structure is used to list which stream configurations support background segmentation when using the **KSPROPERTY_CAMERACONTROL_EXTENDED_BACKGROUNDSEGMENTATION** control so that consumer of this DDI knows what to expect when it is leveraged and in which cases it may not take effect.

If a stream configuration is not listed and the control is set to something other than **KSCAMERA_EXTENDEDPROP_BACKGROUNDSEGMENTATION_OFF**, the DDI may have no effect.

## -struct-fields

### -field Resolution

The width and height of the output format in pixels for which the *MaxFrameRate* and *MaskResolution* apply.

### -field MaxFrameRate

The maximum frame rate the driver can accommodate for achieving background segmentation for each frame corresponding to *Resolution*.

### -field MaskResolution

The width and height of the mask produced when streaming with a MediaType corresponding to *Resolution*.

### -field SubType

Optional subtype for which this configuration capability applies. If left to zero, all streams conforming the *Resolution* and *MaxFrameRate* will support background segmentation with the specified *MaskResolution*.

## -remarks

Two **KSPROPERTY_CAMERACONTROL_EXTENDED_BACKGROUNDSEGMENTATION** controls with the same *Resolution* but different *MaxFrameRate* and *MaskResolution* may be specified to express that different frame rates may produce a different mask resolution.

## -see-also

[KSCAMERA_METADATA_BACKGROUNDSEGMENTATIONMASK](ns-ksmedia-kscamera_metadata_backgroundsegmentationmask.md)
