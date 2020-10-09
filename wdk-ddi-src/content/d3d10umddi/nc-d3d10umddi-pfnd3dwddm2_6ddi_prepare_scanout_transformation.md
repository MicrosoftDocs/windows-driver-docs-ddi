---
UID: NC:d3d10umddi.PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION
title: PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION
description: Invokes the driver to schedule work to perform the necessary transformations from the input resource, to the "shadow" allocation which will actually be scanned out.
tech.root: display
ms.assetid: 84b01acb-e1cb-4ed4-b82c-5dfc427ac05d
ms.date: 04/04/2019
keywords: ["PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION callback function"]
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
 - PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION
 - d3d10umddi/PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION
product:
 - Windows
---

# PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION callback function


## -description

Invokes the driver to schedule work to perform the necessary transformations from the input resource, to the "shadow" allocation which will actually be scanned out. The runtime may request that the driver only update a sub-region, if only a small portion of the resource has changed since the last time this was invoked.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the device.

### -param Arg2

*hResource* [in]

A handle to the resource that is associated with the allocations.

### -param Subresource

The subresource index.

### -param VidPnSourceId

A zero-based ID of the video present source in a path of a video present network topology.

### -param PlaneIdx

The index of the plane.

### -param pSubRect

Pointer to a D3D10_DDI_RECT.

## -prototype

```
//Declaration

PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION Pfnd3dwddm26DdiPrepareScanoutTransformation; 

// Definition

void Pfnd3dwddm26DdiPrepareScanoutTransformation 
(
	D3D10DDI_HDEVICE Arg1
	D3D10DDI_HRESOURCE Arg2
	UINT Subresource
	D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId
	UINT PlaneIdx
	D3D10_DDI_RECT *pSubRect
)
{...}

```

## -remarks

## -see-also

[PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS](nc-d3d10umddi-pfnd3dwddm2_6ddi_query_scanout_caps.md)

