---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
tech.root: stream
title: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
ms.date: 06/24/2021
targetos: Windows
description: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING contains the x and y origin and window size of the digital window in Q24 format.
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
req.typenames: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING, *PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - ksmedia/PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
 - ksmedia/KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING
dev_langs:
 - c++
---

## -description

**KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING** contains the x and y origin and window size of the digital window in Q24 format.

## -struct-fields

### -field OriginX

The origin of the digital window along the x-axis in Q24 format.  Must default to 0.  *OriginX* may not be less than *PorchLeft* nor greater than *PorchRight – WindowSize*.

### -field OriginY

The origin of the digital window along the y-axis in Q24 format.  Must default to 0.  *OriginY* may not be less than *TopPorch* nor greater than *PorchBottom – WindowSize*.

### -field WindowSize

The size of the digital window along both axis in Q24 format. This is the fraction of the full view visible along both the x and y axis.  *WindowSize* must default to 0x01000000 (1.0 in Q24). *WindowSize* may not be less than *MinWindowSize* nor larger than *MaxWindowSize*. In addition, *WindowSize* plus *OriginX* may not be greater than *PorchRight*; *WindowsSize* plus *OriginY* may not be greater than *PorchBottom*.

### -field Reserved

Reserved. Set to 0.

## -remarks

These parameters are read-only if KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_AUTOFACEFRAMING is set in the Flags field.  If KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_AUTOFACEFRAMING is set during a SET operation, the following parameters are ignored.

## -see-also

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcapsheader)

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcaps)

[KSCAMERA_METADATA_DIGITALWINDOW](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_metadata_digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow-configcaps)

[Digital Window overview](/windows-hardware/drivers/stream/digital-window-overview)
