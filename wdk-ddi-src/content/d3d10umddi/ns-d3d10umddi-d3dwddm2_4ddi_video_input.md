---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_INPUT
title: D3DWDDM2_4DDI_VIDEO_INPUT (d3d10umddi.h)
description: Learn more about the D3DWDDM2_4DDI_VIDEO_INPUT structure.
ms.date: 01/17/2023
keywords: ["D3DWDDM2_4DDI_VIDEO_INPUT structure"]
ms.keywords: D3DWDDM2_4DDI_VIDEO_INPUT, D3DWDDM2_4DDI_VIDEO_INPUT,
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
req.typenames: D3DWDDM2_4DDI_VIDEO_INPUT
targetos: Windows
tech.root: display
f1_keywords:
 - D3DWDDM2_4DDI_VIDEO_INPUT
 - d3d10umddi/D3DWDDM2_4DDI_VIDEO_INPUT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_4DDI_VIDEO_INPUT
---

# D3DWDDM2_4DDI_VIDEO_INPUT structure

## -description

**D3DWDDM2_4DDI_VIDEO_INPUT** contains input information used by the [**PFND3D10DDI_RETRIEVESUBOBJECT**](nc-d3d10umddi-pfnd3d10ddi_retrievesubobject.md) DDI when querying the driver's WDDM 2.4 and later video functions.

## -struct-fields

### -field Relocate

Boolean value that indicates whether the functions can be relocated.

### -field pWDDM2_4VideoDeviceFuncs

A pointer to a [**D3DWDDM2_4DDI_VIDEODEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_4ddi_videodevicefuncs.md) structure that contains pointers to the video functions being queried.
