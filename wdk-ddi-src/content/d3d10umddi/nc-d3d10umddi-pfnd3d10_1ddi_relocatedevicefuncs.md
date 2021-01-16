---
UID: NC:d3d10umddi.PFND3D10_1DDI_RELOCATEDEVICEFUNCS
title: PFND3D10_1DDI_RELOCATEDEVICEFUNCS (d3d10umddi.h)
description: The RelocateDeviceFuncs(D3D10_1) function notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d10_1_.htm
ms.date: 05/10/2018
keywords: ["PFND3D10_1DDI_RELOCATEDEVICEFUNCS callback function"]
ms.keywords: PFND3D10_1DDI_RELOCATEDEVICEFUNCS, PFND3D10_1DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs_D3D10_1, RelocateDeviceFuncs_D3D10_1 callback function [Display Devices], UserModeDisplayDriverDx10_Functions_5798bcfe-7d15-407d-b7c2-cfe907e94991.xml, d3d10umddi/RelocateDeviceFuncs_D3D10_1, display.relocatedevicefuncs_d3d10_1_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RelocateDeviceFuncs(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
req.typenames: 
f1_keywords:
 - PFND3D10_1DDI_RELOCATEDEVICEFUNCS
 - d3d10umddi/PFND3D10_1DDI_RELOCATEDEVICEFUNCS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10_1DDI_RELOCATEDEVICEFUNCS
product:
 - Windows
---

# PFND3D10_1DDI_RELOCATEDEVICEFUNCS callback function


## -description

The <i>RelocateDeviceFuncs(D3D10_1)</i> function notifies the user-mode display driver about the new location of the driver function table.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDeviceFunctions* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.


A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D10_1)</i> function to replace function pointers in the driver function table.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

