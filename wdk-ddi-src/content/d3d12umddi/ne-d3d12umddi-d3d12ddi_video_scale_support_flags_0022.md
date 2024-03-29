---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
title: D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 (d3d12umddi.h)
description: Learn more about the D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration.
ms.date: 12/12/2023
keywords: ["D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration"]
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022, D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration [Display Devices], D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0020_NONE, D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY, D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY, display.d3d12ddi_video_scale_support_flags
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
f1_keywords:
 - D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
 - d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration

## -description

The **D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022** enumeration contains the options for video scale support.

## -enum-fields

### -field D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_NONE:0x0

All possible output size width/height combinations that exist between the Max size and Min size for the extent, inclusive, are supported.

### -field D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_POW2_ONLY:0x1

The scaler supports only output sizes at a pow2 scale factors within the range. The x and y scale factors must be the same for both dimensions when this flag is set.

The following is an example that iterates over the supported output sizes for one dimension when this flag is set:

```c
bool OutputSizeSupported(UINT Size, UINT Max, UINT Min)
{
    UINT CurrentSize = Max;
    while (CurrentSize >= Min)
    {
        if (CurrentSize == Size)
        {
            return true;
        }

        CurrentSize = (CurrentSize + 1) / 2;
    }

    return false;
}
```

### -field D3D12DDI_VIDEO_SCALE_SUPPORT_FLAG_0022_EVEN_DIMENSIONS_ONLY:0x2

The scaler supports only output sizes that have even output dimensions.

## -see-also

[**D3D12DDI_VIDEO_SCALE_SUPPORT_0032**](ns-d3d12umddi-d3d12ddi_video_scale_support_0032.md)