---
UID: NS:d3dkmddi._DXGKARG_GETMULTIPLANEOVERLAYCAPS
title: _DXGKARG_GETMULTIPLANEOVERLAYCAPS
author: windows-driver-content
description: Arguments to the DxgkDdiGetMultiPlaneOverlayCaps function.
old-location: display\dxgkarg_getmultiplaneoverlaycaps.htm
old-project: display
ms.assetid: 4792107C-BAAA-48B5-AC9A-829C05795303
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_GETMULTIPLANEOVERLAYCAPS, DXGKARG_GETMULTIPLANEOVERLAYCAPS, *IN_OUT_PDXGKARG_GETMULTIPLANEOVERLAYCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_GETMULTIPLANEOVERLAYCAPS
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGKARG_GETMULTIPLANEOVERLAYCAPS
---

# _DXGKARG_GETMULTIPLANEOVERLAYCAPS structure



## -description
Arguments to the DxgkDdiGetMultiPlaneOverlayCaps function.



## -syntax

````
typedef struct _DXGKARG_GETMULTIPLANEOVERLAYCAPS {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           MaxPlane;
  UINT                           MaxRGBPlanes;
  UINT                           MaxYUVPlanes;
  DXGK_MULTIPLANEOVERLAYCAPS     OverlayCaps;
  float                          MaxStretchFactor;
  float                          MaxShrinkFactor;
} DXGKARG_GETMULTIPLANEOVERLAYCAPS;
````


## -struct-fields

### -field VidPnSourceId

[in] Indicates the VidPn source for which we are querying multiplane overlay capabilities.


### -field MaxPlane

[out] Indicates the total number of planes, including the DWM's primary, that can be supported simultaneously.


### -field MaxRGBPlanes

[out] Indicates the total number of RGB planes, including the DWM’s primary, that can be supported simultaneously.


### -field MaxYUVPlanes

[out] Indicates the total number of YUV planes that can be supported simultaneously.


### -field OverlayCaps

[out] A DXGK_MULTIPLANEOVERLAYCAPS structure indicating the plane capabilities.


### -field MaxStretchFactor

[out] Indicates the maximum stretch factor that can be applied to a plane.


### -field MaxShrinkFactor

[out] Indicates the maximum shrink factor that can be applied to a plane.


## -remarks
