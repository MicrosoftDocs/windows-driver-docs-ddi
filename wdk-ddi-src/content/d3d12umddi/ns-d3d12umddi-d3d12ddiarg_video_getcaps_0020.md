---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_GETCAPS_0020
title: D3D12DDIARG_VIDEO_GETCAPS_0020 (d3d12umddi.h)
description: Specifies values used to get capabilities of a type.
old-location: display\d3d12ddiarg_video_getcaps.htm
ms.date: 02/16/2022
keywords: ["D3D12DDIARG_VIDEO_GETCAPS_0020 structure"]
ms.keywords: D3D12DDIARG_VIDEO_GETCAPS_0020, D3D12DDIARG_VIDEO_GETCAPS_0020 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_GETCAPS_0020, display.d3d12ddiarg_video_getcaps
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
req.typenames: D3D12DDIARG_VIDEO_GETCAPS_0020
f1_keywords:
 - D3D12DDIARG_VIDEO_GETCAPS_0020
 - d3d12umddi/D3D12DDIARG_VIDEO_GETCAPS_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDIARG_VIDEO_GETCAPS_0020
---

# D3D12DDIARG_VIDEO_GETCAPS_0020 structure

## -description

The **D3D12DDIARG_VIDEO_GETCAPS_0020** structure is used to get a specified type of video-related capability/support during a call to a client driver's [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) function.

## -struct-fields

### -field Type

Pointer to a [**D3D12DDICAPS_TYPE_VIDEO_0020**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) value that specifies the video-related capability type.

### -field pInfo

A pointer to a memory block that contains data that specifies the condition on which to retrieve the capabilities of the type that is specified by the **Type** member. Set this field to point to NULL to indicate no condition.

### -field pData

A pointer to a memory block that contains capabilities of the type that is specified by the **Type** member and possibly determined by the condition specified by the **pInfo** member.

### -field DataSize

The size, in bytes, of the memory block at **pData**.

## -remarks

See [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) for examples of the meaning/values of **pInfo**, **pData**, and **DataSize** for various [**D3D12DDICAPS_TYPE_VIDEO_0020**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) types.

## -see-also

[**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md)
