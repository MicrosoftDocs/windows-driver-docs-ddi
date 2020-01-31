---
UID: NC:d3d10umddi.PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS
title: PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS
author: windows-driver-content
description: Queries whether or not a transformation should occur in preparation for a flip operation.
tech.root: display
ms.assetid: 04ec8f9b-6171-4d59-a8b5-32c2e196adf4
ms.author: windowsdriverdev
ms.date: 04/04/2019
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
 - "d3d10umddi/PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS
product:
 - Windows
---

# PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS callback function

## -description

Queries whether or not a transformation should occur in preparation for a flip operation.

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

### -param pFlags

A [D3DWDDM2_6DDI_SCANOUT_FLAGS](ne-d3d10umddi-d3dwddm2_6ddi_scanout_flags.md) value that indicates the type of transformation.

## -prototype

```
//Declaration

PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS Pfnd3dwddm26DdiQueryScanoutCaps; 

// Definition

void Pfnd3dwddm26DdiQueryScanoutCaps 
(
	D3D10DDI_HDEVICE Arg1
	D3D10DDI_HRESOURCE Arg2
	UINT Subresource
	D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId
	UINT PlaneIdx
	D3DWDDM2_6DDI_SCANOUT_FLAGS *pFlags
)
{...}

```

## -remarks

In WDDM 2.6, the D3D11 runtime will be updated to call this DDI prior to issuing a full screen or multiplane overlay flip. If the result is that a transformation is required, or that it’s desired and there’s been no API request to disable it, then the runtime will call [PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION](nc-d3d10umddi-pfnd3dwddm2_6ddi_prepare_scanout_transformation.md).

Note that the runtime will not call PFND3DWDDM2_6DDI_QUERY_SCANOUT_CAPS and PFND3DWDDM2_6DDI_PREPARE_SCANOUT_TRANSFORMATION during a windowed flip model present in Windows 10, version 1903, which may progress to independent flip, because the runtime does not know whether or not that will occur, and if so, which VidPnSource and plane it will use.

The driver may not set both the D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_REQUIRED and D3DWDDM2_6DDI_SCANOUT_FLAG_TRANSFORMATION_DESIRED flag in [D3DWDDM2_6DDI_SCANOUT_FLAGS](ne-d3d10umddi-d3dwddm2_6ddi_scanout_flags.md).

Regardless of whether a transformation occurs, the driver should indicate to the runtime whether the resulting allocation follows a predictable scanout timing or not, by using the D3DWDDM2_6DDI_SCANOUT_FLAG_UNPREDICTABLE_TIMING flag. This information will be used to adjust the front-buffer rendering safety margins.

## -see-also

