---
UID: NS:d3dkmdt._DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
tech.root: display
title: DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO, *PDXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - PDXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
f1_keywords:
 - _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - d3dkmdt/_DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - PDXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - d3dkmdt/PDXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - d3dkmdt/DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
---

## -description

The **DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO** structure contains information about the internal panel.

## -struct-fields

### -field Brightness3Supported

Boolean value that indicates whether the [**DXGK_BRIGHTNESS_INTERFACE_3**](../dispmprt/ns-dispmprt-dxgk_brightness_interface_3.md) is supported by the GPU that the panel was initially connected to at boot time.

### -field Brightness3Caps

If **Brightness3Supported** is TRUE, **Brightness3Caps** is a [**DXGK_BRIGHTNESS_CAPS**](../d3dkmdt/ns-d3dkmdt-_dxgk_brightness_caps.md) structure that contains the reported brigtness 3 capabilities.

### -field Bridgtness3Ranges

If **Brightness3Supported** is TRUE, **Brightness3Ranges** is a [**DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT**](../d3dkmdt/ns-d3dkmdt-_dxgk_brightness_get_nit_ranges_out.md) structure that contains the reported brigtness 3 ranges.

## -remarks

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkddiDisplayMuxSetInternalPanelInfo**](../dispmprt/nc-dispmprt-dxgkddi_displaymux_set_internal_panel_info.md)
