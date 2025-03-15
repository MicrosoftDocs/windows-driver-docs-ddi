---
UID: NE:d3dkmdt._DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL
tech.root: display
title: DXGK_DISPLAYMUX_SUPPORT_LEVEL
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGK_DISPLAYMUX_SUPPORT_LEVEL enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL
 - PDXGK_DISPLAYMUX_SUPPORT_LEVEL
 - DXGK_DISPLAYMUX_SUPPORT_LEVEL
f1_keywords:
 - _DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL
 - d3dkmdt/_DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL
 - PDXGK_DISPLAYMUX_SUPPORT_LEVEL
 - d3dkmdt/PDXGK_DISPLAYMUX_SUPPORT_LEVEL
 - DXGK_DISPLAYMUX_SUPPORT_LEVEL
 - d3dkmdt/DXGK_DISPLAYMUX_SUPPORT_LEVEL
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL
---

## -description

The **DXGK_DISPLAYMUX_SUPPORT_LEVEL** enumeration specifies the level of support that a kernel-mode display driver (KMD) provides for [automatic display switching](/windows-hardware/drivers/display/automatic-display-switch) (ADS).

## -enum-fields

### -field DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL_UNINITIALIZED:0

A variable of this enumeration type hasn't yet been assigned a meaningful value.

### -field DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL_NONE:1

The driver has no support for ADS.

### -field DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL_DEVELOPMENT:2

The driver has development support for ADS, but the quality isn't considered good enough for release. For development purposes only.

### -field DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL_EXPERIMENTAL:3

The driver has experimental support for ADS, but the quality isn't considered good enough for general customer rollout. For testing purposes only.

### -field DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL_FULL:4

The driver has full support for ADS and is ready for general customer rollout.

## -remarks

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkDdiDisplayMuxGetDriverSupportLevel**](../dispmprt/nc-dispmprt-dxgkddi_displaymux_get_driver_support_level.md)
