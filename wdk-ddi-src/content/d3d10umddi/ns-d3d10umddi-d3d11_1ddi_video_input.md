---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_INPUT
tech.root: display
title: D3D11_1DDI_VIDEO_INPUT
ms.date: 01/17/2023
targetos: Windows
description: Learn more about the D3D11_1DDI_VIDEO_INPUT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D11_1DDI_VIDEO_INPUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_INPUT
f1_keywords:
 - D3D11_1DDI_VIDEO_INPUT
 - d3d10umddi/D3D11_1DDI_VIDEO_INPUT
dev_langs:
 - c++
helpviewer_keywords:
 - D3D11_1DDI_VIDEO_INPUT
---

## -description

**D3D11_1DDI_VIDEO_INPUT** contains input information used by the [**PFND3D10DDI_RETRIEVESUBOBJECT**](nc-d3d10umddi-pfnd3d10ddi_retrievesubobject.md) DDI when querying the driver's video functions.

## -struct-fields

### -field Relocate

Boolean value that indicates whether the functions can be relocated.

### -field p11VideoDeviceFuncs

A pointer to a [**D3D11_1DDI_VIDEODEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_videodevicefuncs.md) structure that contains pointers to the video functions being queried.
