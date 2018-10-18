---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
title: D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
author: windows-driver-content
description: Specifies whether alpha blending is enabled and, if so, the planar alpha value.
old-location: display\d3d12ddi_video_process_alpha_blending.htm
ms.assetid: 58E7A600-1CA9-40F8-8F37-CA7A0834B3F4
ms.date: 4/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020, D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020, display.d3d12ddi_video_process_alpha_blending
ms.topic: struct
req.header: d3d12umddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
---

# D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 structure


## -description


Specifies whether alpha blending is enabled and, if so, the planar alpha value.


## -struct-fields




### -field Enable

Specifies whether alpha blending is enabled.


### -field Alpha

The planar alpha value. The value can range from 0.0 (transparent) to 1.0 (opaque). If the <b>Enable</b> member is false, this value is ignored.


## -remarks



For each pixel, the destination color value is computed as the following:

```cpp
Cd = Cs * (As * Ap * Ae) + Cd * (1.0 - As * Ap * Ae)
```


The variables in this equation are as follows:

* **Cd** = The color value of the destination pixel.
* **Cs** = The color value of the source pixel.
* **As** = The per-pixel source alpha.
* **Ap** = The planar alpha value.
* **Ae** = The palette-entry alpha value, or 1.0.


