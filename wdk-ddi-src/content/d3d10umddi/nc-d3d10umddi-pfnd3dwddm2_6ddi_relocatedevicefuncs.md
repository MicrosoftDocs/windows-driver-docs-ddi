---
UID: NC:d3d10umddi.PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS
description: The PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS callback function notifies the user-mode display driver about the new location of the driver function table.
tech.root: display
ms.date: 04/04/2019
keywords: ["PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS callback function"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d10umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: WDDM 2.6, 19H1
f1_keywords:
 - PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS
 - d3d10umddi/PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS
product:
 - Windows
---

# PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS callback function


## -description

The RelocateDeviceFuncs function notifies the user-mode display driver about the new location of the driver function table.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*pDeviceFunctions* [in]

A pointer to a D3DWDDM2_6DDI_DEVICEFUNCS structure that contains pointers to the functions of the user-mode display driver.

## -prototype

```
//Declaration

PFND3DWDDM2_6DDI_RELOCATEDEVICEFUNCS Pfnd3dwddm26DdiRelocatedevicefuncs; 

// Definition

VOID Pfnd3dwddm26DdiRelocatedevicefuncs 
(
	D3D10DDI_HDEVICE Arg1
	D3DWDDM2_6DDI_DEVICEFUNCS *
)
{...}

```

## -remarks

## -see-also

