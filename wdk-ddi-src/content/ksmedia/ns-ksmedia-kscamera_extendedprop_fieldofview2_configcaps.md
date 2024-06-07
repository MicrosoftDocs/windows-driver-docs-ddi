---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
tech.root: stream
title: KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS (ksmedia.h)
ms.date: 03/25/2024
targetos: Windows
description: The KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS structure defines the configuration capabilities of a camera's field of view (FoV).
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS, *PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - ksmedia/PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
 - ksmedia/KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
dev_langs:
 - c++
helpviewer_keywords:
 - tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS
---

## -description

The **KSCAMERA_EXTENDEDPROP_FIELDOFVIEW2_CONFIGCAPS** structure defines the configuration capabilities of a camera's field of view (FoV).

## -struct-fields

### -field DefaultDiagonalFieldOfViewInDegrees

 This is the default diagonal field of view in degrees. The DefaultDiagonalFieldOfViewInDegrees value must be equal to one of the values provided in the DiscreteFoVStops array.

### -field DiscreteFoVStopsCount

This is a count of valid FoVStops in the DiscreteFoVStops[360] array, with value between 1 and 360. The array has room for maximum of 360 FoV values, but not all of them need to be populated.

For example, if three FoV values are supported: 110, 90, and 75 degrees

```cpp
DiscreteFoVStopsCount = 3,
DiscreteFoVStops[0] = 110,
DiscreteFoVStops[1] = 90,
DiscreteFoVStops[2] = 75
DiscreteFoVStops[3] = 0 (not populated)
...
DiscreteFoVStops[359] = 0 (not populated)
```

### -field DiscreteFoVStops[360]

This is an array of discrete FoV stops. Each element in the array represents a specific field of view setting in degrees. The values are populated in descending order.

### -field Reserved

Reserved. Set to 0.

## -remarks

## -see-also

[KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW2](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-fieldofview2)

[KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW2_CONFIGCAPS](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-fieldofview2-configcaps)
