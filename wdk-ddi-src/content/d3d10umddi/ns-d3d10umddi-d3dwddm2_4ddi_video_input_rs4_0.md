---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
title: D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 (d3d10umddi.h)
description: Learn more about the D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 structure.
ms.date: 01/17/2023
keywords: ["D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 structure"]
ms.keywords: D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0, D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0,
req.header: d3d10umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
targetos: Windows
tech.root: display
f1_keywords:
 - D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
 - d3d10umddi/D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
product:
 - Windows
---

# D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 structure

## -description

D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 contains input information used by the [**PFND3D10DDI_RETRIEVESUBOBJECT**](nc-d3d10umddi-pfnd3d10ddi_retrievesubobject.md) DDI when querying the driver's WDDM 2.4 (Windows 10 version 1803) video functions.

## -struct-fields

### -field Relocate

Boolean value that indicates whether the functions can be relocated.

### -field pWDDM2_4VideoDeviceFuncs

A pointer to a [**D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0**](ns-d3d10umddi-d3dwddm2_4ddi_videodevicefuncs_rs4_0.md) structure that contains pointers to the video functions being queried.
