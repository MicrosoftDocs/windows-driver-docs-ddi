---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE_V2
title: DXGK_MONITOR_INTERFACE_V2 (d3dkmddi.h)
description: Learn more about the DXGK_MONITOR_INTERFACE_V2 structure.
ms.date: 06/09/2023
keywords: ["DXGK_MONITOR_INTERFACE_V2 structure"]
ms.keywords: DXGK_MONITOR_INTERFACE_V2, DXGK_MONITOR_INTERFACE_V2 structure [Display Devices], DmStructs_8af61532-16df-472d-abb7-c8f9a677e968.xml, _DXGK_MONITOR_INTERFACE_V2, d3dkmddi/DXGK_MONITOR_INTERFACE_V2, display.dxgk_monitor_interface_v2
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: DXGK_MONITOR_INTERFACE_V2
f1_keywords:
 - _DXGK_MONITOR_INTERFACE_V2
 - d3dkmddi/_DXGK_MONITOR_INTERFACE_V2
 - DXGK_MONITOR_INTERFACE_V2
 - d3dkmddi/DXGK_MONITOR_INTERFACE_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MONITOR_INTERFACE_V2
 - DXGK_MONITOR_INTERFACE_V2
---

# DXGK_MONITOR_INTERFACE_V2 structure

## -description

The **DXGK_MONITOR_INTERFACE_V2** structure contains pointers to functions that belong to the monitor interface, which is implemented by the video present network (VidPN) manager.

## -struct-fields

### -field Version

A value from the [**DXGK_MONITOR_INTERFACE_VERSION**](ne-d3dkmddi-_dxgk_monitor_interface_version.md) enumeration that indicates the monitor interface version. Must be set to 2.

### -field pfnAcquireMonitorSourceModeSet

A pointer to the [**pfnAcquireMonitorSourceModeSet**](nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md) function.

### -field pfnReleaseMonitorSourceModeSet

A pointer to the [**pfnReleaseMonitorSourceModeSet**](nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset.md) function.

### -field pfnGetMonitorFrequencyRangeSet

A pointer to the [**pfnGetMonitorFrequencyRangeSet**](nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md) function.

### -field pfnGetMonitorDescriptorSet

A pointer to the [**pfnGetMonitorDescriptorSet**](nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md) function.

### -field pfnGetAdditionalMonitorModeSet

A pointer to the [**pfnGetAdditionalMonitorModeSet**](nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md) function.

### -field pfnReleaseAdditionalMonitorModeSet

A pointer to the [**pfnReleaseAdditionalMonitorModeSet**](nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset.md) function.

## -remarks

A display miniport driver must verify the interface version specified in the **Version** member before using this structure.

## -see-also

[**DXGK_MONITOR_INTERFACE**](ns-d3dkmddi-_dxgk_monitor_interface.md)
