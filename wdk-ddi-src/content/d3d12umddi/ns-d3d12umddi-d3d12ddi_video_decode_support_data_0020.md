---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
title: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 (d3d12umddi.h)
description: Specifies data used to determine support of hardware for a configuration.
old-location: display\d3d12ddi_video_decode_support_data.htm
ms.assetid: 05274F4B-0473-42BA-A382-B348A85DBFA5
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020, D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020, display.d3d12ddi_video_decode_support_data
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
req.typenames: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
f1_keywords:
 - D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
 - d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure


## -description

Specifies data used to determine support of hardware for a configuration. Used by the [PFND3D12DDI_VIDEO_GETCAPS](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) callback function, with the *Type* parameter in [D3D12DDIARG_VIDEO_GETCAPS_0020](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md) set to D3D12DDICAPS_TYPE_VIDEO_DECODE_SUPPORT.

## -struct-fields

### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

### -field Configuration

The decode profile and bitstream encryption. For more information, see [D3D12DDI_VIDEO_DECODE_CONFIGURATION](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md).

### -field Width

The decode width of the source stream.

### -field Height

The decode height of the source stream.

### -field DecodeFormat

The DirectX resource data format to use as the decode format. If no decoder conversion is specified, this format is the output format.

### -field FrameRate

The frame rate of the video format. Used to help return performance hints in the <b>SupportFlags</b> member. A value of zero (0) means unknown.

### -field BitRate

The average bits per second data compression rate for the compressed video stream. This is used by the driver to determine whether the video can be decoded in real time. A value of zero (0) means unknown.

### -field SupportFlags

Supported flags. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020">D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS</a>.

### -field ConfigurationFlags

Configuration flags. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS</a>.

### -field DecodeTier

The tier supported by this configuration.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_tier_0020">D3D12DDI_VIDEO_DECODE_TIER</a>.

## -remarks

This structure is retrieved through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_video_getcaps">pfnGetCaps</a> callback function  with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddicaps_type">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_SUPPORT</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



<b>D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020">D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_tier_0020">D3D12DDI_VIDEO_DECODE_TIER</a>

