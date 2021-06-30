---
UID: NS:ksmedia.tagKSCAMERA_METADATA_DIGITALWINDOW
tech.root: stream
title: KSCAMERA_METADATA_DIGITALWINDOW
ms.date: 06/24/2021
targetos: Windows
description: KSCAMERA_METADATA_DIGITALWINDOW contains metadata header information along with the digital window x and y origin and size in Q24 format.
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
req.typenames: KSCAMERA_METADATA_DIGITALWINDOW, *PKSCAMERA_METADATA_DIGITALWINDOW
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSCAMERA_METADATA_DIGITALWINDOW
 - PKSCAMERA_METADATA_DIGITALWINDOW
 - KSCAMERA_METADATA_DIGITALWINDOW
f1_keywords:
 - tagKSCAMERA_METADATA_DIGITALWINDOW
 - ksmedia/tagKSCAMERA_METADATA_DIGITALWINDOW
 - PKSCAMERA_METADATA_DIGITALWINDOW
 - ksmedia/PKSCAMERA_METADATA_DIGITALWINDOW
 - KSCAMERA_METADATA_DIGITALWINDOW
 - ksmedia/KSCAMERA_METADATA_DIGITALWINDOW
dev_langs:
 - c++
---

## -description

**KSCAMERA_METADATA_DIGITALWINDOW** contains metadata header information along with the digital window x and y origin and size in Q24 format.

## -struct-fields

### -field Header

A [KSCAMERA_METADATA_ITEMHEADER](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagkscamera_metadata_itemheader) structure that contains the metadata header information that is filled by the camera driver.

### -field Window

A [KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_setting) structure that contains the x and y origin and size of the digital window in Q24 format.

## -see-also

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPSHEADER](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcapsheader)

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_configcaps)

[KSCAMERA_EXTENDEDPROP_DIGITALWINDOW_SETTING](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_extendedprop_digitalwindow_setting)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow)

[KSPROPERTY_CAMERACONTROL_EXTENDED_DIGITALWINDOW_CONFIGCAPS](/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-digitalwindow-configcaps)

[Digital Window overview](/windows-hardware/drivers/stream/digital-window-overview)
