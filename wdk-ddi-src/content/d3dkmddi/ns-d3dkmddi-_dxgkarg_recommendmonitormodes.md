---
UID: NS:d3dkmddi._DXGKARG_RECOMMENDMONITORMODES
title: _DXGKARG_RECOMMENDMONITORMODES (d3dkmddi.h)
description: The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the DxgkDdiRecommendMonitorModes function.
old-location: display\dxgkarg_recommendmonitormodes.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_RECOMMENDMONITORMODES structure"]
ms.keywords: DXGKARG_RECOMMENDMONITORMODES, DXGKARG_RECOMMENDMONITORMODES structure [Display Devices], DmStructs_151c48fa-735a-4962-9fe7-446830441f1c.xml, _DXGKARG_RECOMMENDMONITORMODES, d3dkmddi/DXGKARG_RECOMMENDMONITORMODES, display.dxgkarg_recommendmonitormodes
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
targetos: Windows
tech.root: display
req.typenames: DXGKARG_RECOMMENDMONITORMODES
f1_keywords:
 - _DXGKARG_RECOMMENDMONITORMODES
 - d3dkmddi/_DXGKARG_RECOMMENDMONITORMODES
 - DXGKARG_RECOMMENDMONITORMODES
 - d3dkmddi/DXGKARG_RECOMMENDMONITORMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_RECOMMENDMONITORMODES
---

# _DXGKARG_RECOMMENDMONITORMODES structure


## -description

The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendmonitormodes">DxgkDdiRecommendMonitorModes</a> function.

## -struct-fields

### -field VideoPresentTargetId

An integer that identifies a video present target on the display adapter.

### -field hMonitorSourceModeSet

A handle to a monitor source mode set object. This set contains a list of modes that are supported by the monitor that is connected to the video present target identified by <i>VideoPresentTargetId</i>.

### -field pMonitorSourceModeSetInterface

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can use to inspect, and possibly add modes to, the monitor source mode set.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendmonitormodes">DxgkDdiRecommendMonitorModes</a>
