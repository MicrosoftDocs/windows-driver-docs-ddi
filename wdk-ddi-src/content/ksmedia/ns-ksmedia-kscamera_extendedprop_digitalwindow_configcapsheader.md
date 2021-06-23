---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
tech.root: stream
title: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
ms.date: 06/24/2021
targetos: Windows
description: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER contains size  and count information for the KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER and KSCAMERA_EXTENDEDPROP_DIGITAL_WINDOW_CONFIGCAPS structures.
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
req.typenames: KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER, *PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
f1_keywords:
 - tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - ksmedia/tagKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - ksmedia/PKSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
 - ksmedia/KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER
dev_langs:
 - c++
---

## -description

**KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER** contains size and count information for the **KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER** and [KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcaps) structures.

## -struct-fields

### -field Size

The size in bytes of this structure plus all other structures that follow.

### -field Count

The number of **KSCAMERA_EXTENDEDPROP_DIGITAL_WINDOW_CONFIGCAPS** structures that follow.

## -see-also

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcaps)

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_setting)

[KSCAMERA_METADATA_DIGITALWINDOW](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_metadata_digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow-configcaps)

[Digital Window overview](/windows-hardware/drivers/stream/digital-window-overview)
