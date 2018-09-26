---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE_VIDEO_0020
title: D3D12DDICAPS_TYPE_VIDEO_0020
author: windows-driver-content
description: Contains capability types for video.
old-location: display\d3d12ddicaps_type_video_0020.htm
ms.assetid: 3B95996D-EB7C-4DCF-B00C-BA5AFEFD4110
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDICAPS_TYPE_VIDEO_0020, D3D12DDICAPS_TYPE_VIDEO_0020 enumeration [Display Devices], D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT, display.d3d12ddicaps_type_video_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D12DDICAPS_TYPE_VIDEO_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDICAPS_TYPE_VIDEO_0020
---

# D3D12DDICAPS_TYPE_VIDEO_0020 enumeration


## -description


Contains capability types for video.


## -enum-fields




### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT

Check if a decode profile, bitstream encryption, resolution, and format are supported. The result is a [D3D12DDI_VIDEO_DECODE_TIER_0020](ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md) that indicates the level of support. The associated data structure is [D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020](../d3d12umddi/ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES

Retrieve the list of decode profiles supported by the adapter. Use [ID3D12Device1::GetVideoDecoderProfileCount](https://msdn.microsoft.com/en-us/library/windows/desktop/hh447796(v=vs.85).aspx) to get the number of profiles before calling check feature support. The associated data structure is [D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020](ns-d3d12umddi-d3d12ddi_video_decode_profiles_data_0020.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS

Retrieve the list of supported decode formats for a [D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md) structure. Use [ID3D12Device1::GetVideoDecoderProfileCount](https://msdn.microsoft.com/en-us/library/windows/desktop/hh447796(v=vs.85).aspx) to get the number of profiles before calling check feature support.


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT

Check whether a color space conversion, format conversion, and scale are supported. The associated data structure is [D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032](ns-d3d12umddi-d3d12ddi_video_decode_conversion_support_data_0032.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES

Retrieve the list of bitstream encryption schemes that are supported by the adapter. The associated data structure is [D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020](ns-d3d12umddi-d3d12ddi_video_decode_bitstream_encryption_schemes_data_0020.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT

Retrieve the video processor capabilities. The associated data structure is [D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA](ns-d3d12umddi-d3d12ddi_video_process_support_data_0032.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS

The maximum number of streams that can be enabled at the same time. The associated data structure is [D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA](ns-d3d12umddi-d3d12ddi_video_process_max_input_streams_data_0020.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO

Retrieves the number of past and future frames required for a given deinterlace mode, filters, frame rate conversion, and features. The associated data structure is [D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA](ns-d3d12umddi-d3d12ddi_video_process_reference_info_data_0020.md).


### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE

The video decoder heap size. Maps to the [D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033](ns-d3d12umddi-d3d12ddi_video_decoder_heap_size_data_0033.md) structure. The size of the video decoder heap is static at compile time.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_PROCESSOR_SIZE

The video decoder processor size. Maps to the [D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0032](ns-d3d12umddi-d3d12ddi_video_processor_size_data_0032.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_PROFILE_COUNT

The video decode profile count. Maps to the [D3D12DDI_VIDEO_ DECODE_PROFILE_COUNT_DATA](ns-d3d12umddi-d3d12ddi_video_decode_profile_count_data_0032.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_FORMAT_COUNT

The video decode format count. Maps to the [D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032](ns-d3d12umddi-d3d12ddi_video_decode_format_count_data_0032.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT

The video decode bitstream encryption scheme count. Maps to the [D3D12DDI_VIDEO_ DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA](ns-d3d12umddi-d3d12ddi_video_decode_bitstream_encryption_schemes_data_0020.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_SUPPORT

The video crypto session support. Maps to the [D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_crypto_session_support_data_0030.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_COUNT

The video content protection system count. Maps to the [D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_COUNT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_content_protection_system_count_data_0030.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_SUPPORT

The video content protection system support. Maps to the [D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_content_protection_system_support_data_0030.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_TRANSFORM_SUPPORT

The video crypto session transform support. Maps to the [D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_crypto_session_transform_support_data_0030.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0040_DECODE_HISTOGRAM

The video decode histogram data. Maps to the [D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041](ns-d3d12umddi-d3d12ddi_video_decode_histogram_data_0041.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0053_FEATURE_AREA_SUPPORT 

The video feature area support.

### -field D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR 

The video motion estimator caps check.

### -field D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR_SIZE 

The video motion estimator size caps check.