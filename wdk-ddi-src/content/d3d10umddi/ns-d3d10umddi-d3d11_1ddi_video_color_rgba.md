---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_COLOR_RGBA
title: D3D11_1DDI_VIDEO_COLOR_RGBA
author: windows-driver-content
description: Specifies an RGB color value.
old-location: display\d3d11_1ddi_video_color_rgba.htm
old-project: display
ms.assetid: 0d97d6ef-87e6-4ba3-ab4b-aa5b22cb126b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_COLOR_RGBA, D3D11_1DDI_VIDEO_COLOR_RGBA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_COLOR_RGBA
req.alt-loc: D3d10umddi.h
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
req.typenames: D3D11_1DDI_VIDEO_COLOR_RGBA
---

# D3D11_1DDI_VIDEO_COLOR_RGBA structure



## -description
Specifies an RGB color value.



## -syntax

````
typedef struct D3D11_1DDI_VIDEO_COLOR_RGBA {
  float R;
  float G;
  float B;
  float A;
} D3D11_1DDI_VIDEO_COLOR_RGBA;
````


## -struct-fields

### -field R

The red value.


### -field G

The green value.


### -field B

The blue value.


### -field A

The alpha value. Values range from 0 (transparent) to 1 (opaque).



## -remarks
