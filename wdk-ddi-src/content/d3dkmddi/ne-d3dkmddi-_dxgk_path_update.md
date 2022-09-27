---
UID: NE:d3dkmddi._DXGK_PATH_UPDATE
title: DXGK_PATH_UPDATE (d3dkmddi.h)
description: Enum which indicates how this path has been modified since the previous successful call to SetTimingsFromVidPn.
old-location: display\dxgk_path_update.htm
ms.date: 08/25/2022
keywords: ["DXGK_PATH_UPDATE enumeration"]
ms.keywords: DXGK_PATH_UPDATE, DXGK_PATH_UPDATE enumeration [Display Devices], DXGK_PATH_UPDATE_ADDED, DXGK_PATH_UPDATE_MODIFIED, DXGK_PATH_UPDATE_REMOVED, DXGK_PATH_UPDATE_UNMODIFED, _DXGK_PATH_UPDATE, d3dkmddi/DXGK_PATH_UPDATE, d3dkmddi/DXGK_PATH_UPDATE_ADDED, d3dkmddi/DXGK_PATH_UPDATE_MODIFIED, d3dkmddi/DXGK_PATH_UPDATE_REMOVED, d3dkmddi/DXGK_PATH_UPDATE_UNMODIFED, display.dxgk_path_update
req.header: d3dkmddi.h
req.include-header: 
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
tech.root: display
req.typenames: DXGK_PATH_UPDATE
f1_keywords:
 - _DXGK_PATH_UPDATE
 - d3dkmddi/_DXGK_PATH_UPDATE
 - DXGK_PATH_UPDATE
 - d3dkmddi/DXGK_PATH_UPDATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_PATH_UPDATE
 - DXGK_PATH_UPDATE
---

# DXGK_PATH_UPDATE enumeration

## -description

Enum which indicates how this path has been modified since the previous successful call to [**SetTimingsFromVidPn**](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md).

## -enum-fields

### -field DXGK_PATH_UPDATE_UNMODIFIED

Indicates that this path has not been changed since the last call to [**SetTimingsFromVidPn**](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md).  This allows the driver to skip interrogating VidPn for changes. Existing scan-out should continue, other than any glitching which might be caused due to reassignment of display resources to satisfy other paths.

### -field DXGK_PATH_UPDATE_ADDED

Indicates that this path is new so the driver will have to fully comprehend the description of what is required. Since there is no allocation from which to scan out, the driver must scan out black until the OS associates one or more planes to be scanned out.

### -field DXGK_PATH_UPDATE_MODIFIED

Indicates that this path has been changed since the last call to [**SetTimingsFromVidPn**](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md). The driver will have to interrogate the VidPn and check the other path info fields in order to understand what has changed.  The OS will have removed all pixel planes prior to making this call so the driver must scan out black until the OS associates one or more planes to be scanned out.

### -field DXGK_PATH_UPDATE_REMOVED

Indicates that this path was present in the previous VidPn but has been removed. The driver should be able to optimize the removal without interrogating VidPn to see that the path has been removed.
