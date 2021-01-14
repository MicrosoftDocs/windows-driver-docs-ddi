---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE_V2
title: _DXGK_MONITOR_INTERFACE_V2 (d3dkmddi.h)
description: The DXGK_MONITOR_INTERFACE_V2 structure, available beginning with Windows 7, contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitor_interface_v2.htm
ms.date: 05/10/2018
keywords: ["DXGK_MONITOR_INTERFACE_V2 structure"]
ms.keywords: DXGK_MONITOR_INTERFACE_V2, DXGK_MONITOR_INTERFACE_V2 structure [Display Devices], DmStructs_8af61532-16df-472d-abb7-c8f9a677e968.xml, _DXGK_MONITOR_INTERFACE_V2, d3dkmddi/DXGK_MONITOR_INTERFACE_V2, display.dxgk_monitor_interface_v2
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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

# _DXGK_MONITOR_INTERFACE_V2 structure


## -description

The DXGK_MONITOR_INTERFACE_V2 structure, available beginning with Windows 7, contains pointers to functions that belong to the <a href="/windows-hardware/drivers/ddi/index">Monitor Interface</a>, which is implemented by the video present network (VidPN) manager.

## -struct-fields

### -field Version

A value from the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_monitor_interface_version">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that indicates the monitor interface version. Must be set to 2.

### -field pfnAcquireMonitorSourceModeSet

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function.

### -field pfnReleaseMonitorSourceModeSet

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset">pfnReleaseMonitorSourceModeSet</a> function.

### -field pfnGetMonitorFrequencyRangeSet

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset">pfnGetMonitorFrequencyRangeSet</a> function.

### -field pfnGetMonitorDescriptorSet

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset">pfnGetMonitorDescriptorSet</a> function.

### -field pfnGetAdditionalMonitorModeSet

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset">pfnGetAdditionalMonitorModeSet</a> function.

### -field pfnReleaseAdditionalMonitorModeSet

A pointer to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset">pfnReleaseAdditionalMonitorModeSet</a> function.

## -remarks

<div class="alert"><b>Note</b>    A display miniport driver must verify the interface version specified in the <b>Version</b> member before using this structure. This structure is available beginning with Windows 7.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface">DXGK_MONITOR_INTERFACE</a>

