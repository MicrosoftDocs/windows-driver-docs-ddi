---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
title: D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
author: windows-driver-content
description: D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 contains the JPEG image function table that is provided to the Microsoft DirectX graphics kernel by the user mode driver.
ms.assetid: b070b756-c72f-4065-b16d-58a3f39e62e0
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 structure

## -description

D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0 contains the JPEG image function table that is provided to the Microsoft DirectX graphics kernel by the user mode driver.

## -struct-fields

### -field Relocate

Indicates that the functions can be relocated.

### -field pWDDM2_4VideoDeviceFuncs

A pointer to a D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0 structure that contains the image function pointers.

## -remarks

## -see-also

[D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0](ns-d3d10umddi-d3dwddm2_4ddi_videodevicefuncs_rs4_0.md)