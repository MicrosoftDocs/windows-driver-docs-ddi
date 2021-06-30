---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
tech.root: stream
title: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
ms.date: 06/24/2021
targetos: Windows
description: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS defines an available resolution and its supported configuration values.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr:
req.target-type: 
req.typenames: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS, *PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - ksmedia/PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
 - ksmedia/KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS
dev_langs:
 - c++
---

## -description

**KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS** defines an available resolution and its supported configuration values.

## -struct-fields

### -field ResolutionX

The width of the output format in pixels.

### -field ResolutionY

The height of the output format in pixels.

### -field PorchTop

The upper limit of the camera sensor's overscan region expressed as a fraction of the total field of view along the y-axis.  This value must be less than or equal to 0.0 in Q24 format.

### -field PorchLeft

The left-most limit of the camera sensor's overscan region expressed as a fraction of the total field of view along the x-axis.  This value must be less than or equal to 0.0 in Q24 format.

### -field PorchBottom

The lower limit of the camera sensor's overscan region expressed as a fraction of the total field of view along the y-axis.  This value must be greater than or equal to 1.0 in Q24 format.

### -field PorchRight

The right-most limit of the camera sensor's overscan region expressed as a fraction of the total field of view along the x-axis.  This value must be greater than or equal to 1.0 in Q24 format

### -field NonUpscalingWindowSize

The value an application should set as the *WindowSize* so it can acquire an image that returns the full fidelity of the sensor.  The value is expressed as a Q24 value, between *MinWindowSize* and *MaxWindowSize*.  

### -field MinWindowSize

The smallest *WindowSize* the Digital Window control can support for this resolution.  This value may be any number greater than 0.0 but less than or equal to 1.0.

### -field MaxWindowSize

The largest *WindowSize* the Digital Window control can support for this resolution.  This value must be 1.0 or greater.

### -field Reserved

Reserved. Set to 0.

## -see-also

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcapsheader)

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_setting)

[KSCAMERA_METADATA_DIGITALWINDOW](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_metadata_digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow-configcaps)

[Digital Window overview](/windows-hardware/drivers/stream/digital-window-overview)
