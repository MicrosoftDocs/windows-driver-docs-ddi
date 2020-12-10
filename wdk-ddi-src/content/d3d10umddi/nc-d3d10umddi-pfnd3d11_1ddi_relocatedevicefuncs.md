---
UID: NC:d3d10umddi.PFND3D11_1DDI_RELOCATEDEVICEFUNCS
title: PFND3D11_1DDI_RELOCATEDEVICEFUNCS (d3d10umddi.h)
description: Notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d11_1_.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_RELOCATEDEVICEFUNCS callback function"]
ms.keywords: PFND3D11_1DDI_RELOCATEDEVICEFUNCS, PFND3D11_1DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs(D3D11_1), RelocateDeviceFuncs(D3D11_1) callback function [Display Devices], d3d10umddi/RelocateDeviceFuncs(D3D11_1), display.pfnrelocatedevicefuncs, display.relocatedevicefuncs_d3d11_1_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - PFND3D11_1DDI_RELOCATEDEVICEFUNCS
 - d3d10umddi/PFND3D11_1DDI_RELOCATEDEVICEFUNCS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - RelocateDeviceFuncs(D3D11_1)
product:
 - Windows
---

# PFND3D11_1DDI_RELOCATEDEVICEFUNCS callback function


## -description

Notifies the user-mode display driver about the new location of the driver function table.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDeviceFunctions* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.


A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11_1)</i> function to replace function pointers in the driver function table.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
