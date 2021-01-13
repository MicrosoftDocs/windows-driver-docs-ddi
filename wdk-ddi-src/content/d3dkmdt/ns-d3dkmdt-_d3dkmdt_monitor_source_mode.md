---
UID: NS:d3dkmdt._D3DKMDT_MONITOR_SOURCE_MODE
title: _D3DKMDT_MONITOR_SOURCE_MODE (d3dkmdt.h)
description: The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode.
old-location: display\d3dkmdt_monitor_source_mode.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_MONITOR_SOURCE_MODE structure"]
ms.keywords: D3DKMDT_MONITOR_SOURCE_MODE, D3DKMDT_MONITOR_SOURCE_MODE structure [Display Devices], DmStructs_165795ef-f70e-4f50-a35f-c6009c547be2.xml, _D3DKMDT_MONITOR_SOURCE_MODE, d3dkmdt/D3DKMDT_MONITOR_SOURCE_MODE, display.d3dkmdt_monitor_source_mode
req.header: d3dkmdt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: D3DKMDT_MONITOR_SOURCE_MODE
f1_keywords:
 - _D3DKMDT_MONITOR_SOURCE_MODE
 - d3dkmdt/_D3DKMDT_MONITOR_SOURCE_MODE
 - D3DKMDT_MONITOR_SOURCE_MODE
 - d3dkmdt/D3DKMDT_MONITOR_SOURCE_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_MONITOR_SOURCE_MODE
---

# _D3DKMDT_MONITOR_SOURCE_MODE structure


## -description

The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode.

## -struct-fields

### -field Id

An integer that identifies the monitor source mode.

### -field VideoSignalInfo

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_signal_info">D3DKMDT_VIDEO_SIGNAL_INFO</a> enumerator that indicates the video mode standard (if any) that defines the mode.

### -field ColorBasis

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_color_basis">D3DKMDT_COLOR_BASIS</a> enumerator that indicates the color basis of the mode.

### -field ColorCoeffDynamicRanges

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_color_coeff_dynamic_ranges">D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES</a> structure that contains the dynamic ranges for the color channels in the mode's color basis.

### -field Origin

A value from the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> enumeration that indicates the source of the mode information. For example the mode information could be from a default monitor profile or it could be from an override in an INF file.

### -field Preference

A value from the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_mode_preference">D3DKMDT_MODE_PREFERENCE</a> enumeration that indicates whether the mode is the preferred mode in a <a href="/windows-hardware/drivers/ddi/index">monitor source mode set</a>.

## -remarks

The D3DKMDT_MONITOR_SOURCE_MODE_ID data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>
