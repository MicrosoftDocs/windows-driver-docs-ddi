---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE
title: DXGK_MONITOR_INTERFACE (d3dkmddi.h)
description: Learn more about the DXGK_MONITOR_INTERFACE structure.
ms.date: 06/09/2023
keywords: ["DXGK_MONITOR_INTERFACE structure"]
ms.keywords: DXGK_MONITOR_INTERFACE, DXGK_MONITOR_INTERFACE structure [Display Devices], DmStructs_23906e50-4f65-4483-a54c-915f9fd3c433.xml, _DXGK_MONITOR_INTERFACE, d3dkmddi/DXGK_MONITOR_INTERFACE, display.dxgk_monitor_interface
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: DXGK_MONITOR_INTERFACE
f1_keywords:
 - _DXGK_MONITOR_INTERFACE
 - d3dkmddi/_DXGK_MONITOR_INTERFACE
 - DXGK_MONITOR_INTERFACE
 - d3dkmddi/DXGK_MONITOR_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MONITOR_INTERFACE
 - DXGK_MONITOR_INTERFACE
---

# DXGK_MONITOR_INTERFACE structure

## -description

The **DXGK_MONITOR_INTERFACE** structure contains pointers to functions that belong to the monitor Interface, which is implemented by the video present network (VidPN) manager.

## -struct-fields

### -field Version

A value from the [**DXGK_MONITOR_INTERFACE_VERSION**](ne-d3dkmddi-_dxgk_monitor_interface_version.md) enumeration that indicates the monitor interface version. Must be set to 1.

### -field pfnAcquireMonitorSourceModeSet

A pointer to the [**pfnAcquireMonitorSourceModeSet**](nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md) function.

### -field pfnReleaseMonitorSourceModeSet

A pointer to the [**pfnReleaseMonitorSourceModeSet**](nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset.md) function.

### -field pfnGetMonitorFrequencyRangeSet

A pointer to the [**pfnGetMonitorFrequencyRangeSet**](nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md) function.

### -field pfnGetMonitorDescriptorSet

A pointer to the [**pfnGetMonitorDescriptorSet**](nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md) function.

## -remarks

A display miniport driver must verify the interface version specified in the **Version** member before using this structure.

## -see-also

[**DXGK_MONITOR_INTERFACE_V2**](ns-d3dkmddi-_dxgk_monitor_interface_v2.md)
