---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS (d3d10umddi.h)
description: The pfnRelocateDeviceFuncs callback function specifies the device functions table.
old-location: display\pfnd3dwddm2_2ddi_relocatedevicefuncs.htm
ms.assetid: EAABE65C-3893-4B4C-BB7E-A02F91F869BE
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback function"]
ms.keywords: PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS, PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback, d3d10umddi/pfnRelocateDeviceFuncs, display.pfnd3dwddm2_2ddi_relocatedevicefuncs, pfnRelocateDeviceFuncs, pfnRelocateDeviceFuncs callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
 - "d3d10umddi/pfnRelocateDeviceFuncs"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - pfnRelocateDeviceFuncs
product:
 - Windows
---

# PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback function

## -description

The <i>pfnRelocateDeviceFuncs</i> callback function specifies the device functions table.

## -parameters

### -param Arg1

*hDevice*

A handle to the display device (graphics context).

### -param Arg2

*DeviceFunctions* [in]

The device functions table, as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs">D3DWDDM2_2DDI_DEVICEFUNCS</a>

