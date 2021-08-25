---
UID: NS:d3dkmddi._DXGK_DISPLAY_DRIVERCAPS_EXTENSION
title: _DXGK_DISPLAY_DRIVERCAPS_EXTENSION (d3dkmddi.h)
description: Driver capabilities extension for WDDM 2.0 or later drivers.
ms.date: 08/25/2021
keywords: ["DXGK_DISPLAY_DRIVERCAPS_EXTENSION structure"]
ms.keywords: _DXGK_DISPLAY_DRIVERCAPS_EXTENSION, DXGK_DISPLAY_DRIVERCAPS_EXTENSION,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_DISPLAY_DRIVERCAPS_EXTENSION
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _DXGK_DISPLAY_DRIVERCAPS_EXTENSION
 - d3dkmddi/_DXGK_DISPLAY_DRIVERCAPS_EXTENSION
 - DXGK_DISPLAY_DRIVERCAPS_EXTENSION
 - d3dkmddi/DXGK_DISPLAY_DRIVERCAPS_EXTENSION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_DISPLAY_DRIVERCAPS_EXTENSION
 - DXGK_DISPLAY_DRIVERCAPS_EXTENSION
dev_langs:
 - c++
---

# _DXGK_DISPLAY_DRIVERCAPS_EXTENSION structure


## -description

Driver capabilities extension for WDDM 2.0 or later drivers.

## -struct-fields

### -field SecureDisplaySupport

This flag indicates that miniport wants to support secure display connection.

### -field VirtualModeSupport

Indicates the virtual display mode support.

### -field NonSpecificPrimarySupport

Indicates non-specific primary support.

### -field HdrFP16ScanoutSupport

HDR pixel format scanout capability support.

### -field HdrARGB10ScanoutSupport

The display is HDR capable.

### -field SupportUsb4Targets

Indicates USB4 targets support. This value is only valid for WDDM 3.0 drivers.

### -field Reserved

Reserved.

### -field Value

## -remarks

## -see-also

