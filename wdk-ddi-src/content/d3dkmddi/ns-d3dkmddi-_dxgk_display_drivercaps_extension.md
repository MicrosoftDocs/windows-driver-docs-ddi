---
UID: NS:d3dkmddi._DXGK_DISPLAY_DRIVERCAPS_EXTENSION
title: _DXGK_DISPLAY_DRIVERCAPS_EXTENSION (d3dkmddi.h)
description: Driver capabilities extension for WDDM 2.0 or later drivers.
ms.assetid: a4a74c3b-1fb6-4b0c-ba50-efa5648da9fd
ms.date: 10/19/2018
keywords: ["DXGK_DISPLAY_DRIVERCAPS_EXTENSION structure"]
f1_keywords:
 - "d3dkmddi/_DXGK_DISPLAY_DRIVERCAPS_EXTENSION"
 - "_DXGK_DISPLAY_DRIVERCAPS_EXTENSION"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmddi.h
api_name: 
- _DXGK_DISPLAY_DRIVERCAPS_EXTENSION
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
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

### -field Reserved

Reserved.
 
### -field Value
 

## -remarks

## -see-also
