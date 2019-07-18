---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE
title: _DXGK_MONITOR_INTERFACE (d3dkmddi.h)
description: The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitor_interface.htm
ms.assetid: edb6df63-7354-4da3-b641-2ce7f28ca7e8
ms.date: 05/10/2018
ms.keywords: DXGK_MONITOR_INTERFACE, DXGK_MONITOR_INTERFACE structure [Display Devices], DmStructs_23906e50-4f65-4483-a54c-915f9fd3c433.xml, _DXGK_MONITOR_INTERFACE, d3dkmddi/DXGK_MONITOR_INTERFACE, display.dxgk_monitor_interface
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_MONITOR_INTERFACE"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_MONITOR_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MONITOR_INTERFACE
---

# _DXGK_MONITOR_INTERFACE structure


## -description


The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor Interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field Version

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_monitor_interface_version">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that indicates the monitor interface version. Must be set to 1.


### -field pfnAcquireMonitorSourceModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function.


### -field pfnReleaseMonitorSourceModeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset">pfnReleaseMonitorSourceModeSet</a> function.


### -field pfnGetMonitorFrequencyRangeSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset">pfnGetMonitorFrequencyRangeSet</a> function.


### -field pfnGetMonitorDescriptorSet

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset">pfnGetMonitorDescriptorSet</a> function.


## -remarks



<div class="alert"><b>Note</b>    A display miniport driver must verify the interface version specified in the <b>Version</b> member before using <p class="note">this structure.

</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_monitor_interface_version">DXGK_MONITOR_INTERFACE_VERSION</a>
 

 

