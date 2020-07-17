---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDMONITORMODES
title: DXGKDDI_RECOMMENDMONITORMODES (d3dkmddi.h)
description: The DxgkDdiRecommendMonitorModes function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set.
old-location: display\dxgkddirecommendmonitormodes.htm
ms.assetid: 1fa29ab6-1faa-4be6-ae87-4cac9057471d
ms.date: 05/10/2018
keywords: ["DXGKDDI_RECOMMENDMONITORMODES callback function"]
ms.keywords: DXGKDDI_RECOMMENDMONITORMODES, DXGKDDI_RECOMMENDMONITORMODES callback, DmFunctions_0e8f1382-ec41-4953-8e1e-f2a5121acc0c.xml, DxgkDdiRecommendMonitorModes, DxgkDdiRecommendMonitorModes callback function [Display Devices], d3dkmddi/DxgkDdiRecommendMonitorModes, display.dxgkddirecommendmonitormodes
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiRecommendMonitorModes"
 - "DxgkDdiRecommendMonitorModes"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiRecommendMonitorModes
product:
 - Windows
---

# DXGKDDI_RECOMMENDMONITORMODES callback function

## -description

The <i>DxgkDdiRecommendMonitorModes</i> function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pRecommendMonitorModes

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_recommendmonitormodes">DXGKARG_RECOMMENDMONITORMODES</a> structure that contains function arguments.

## -returns

<i>DxgkDdiRecommendMonitorModes</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_NO_MEMORY|The function failed because it was unable to allocate enough memory.|

The miniport driver should pass through any error code that it gets from the operating system for which it does not have a fallback code path.

## -remarks

<i>DxgkDdiRecommendMonitorModes</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor Source Mode Set Interface</a>

