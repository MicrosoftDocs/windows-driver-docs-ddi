---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE_VIDEO_0020
title: D3D12DDICAPS_TYPE_VIDEO_0020 (d3d12umddi.h)
description: Contains capability types for video.
old-location: display\d3d12ddicaps_type_video_0020.htm
ms.date: 02/16/2022
keywords: ["D3D12DDICAPS_TYPE_VIDEO_0020 enumeration"]
ms.keywords: D3D12DDICAPS_TYPE_VIDEO_0020, D3D12DDICAPS_TYPE_VIDEO_0020 enumeration [Display Devices], D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT, display.d3d12ddicaps_type_video_0020
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
req.typenames: D3D12DDICAPS_TYPE_VIDEO_0020
ms.custom: 19H1
f1_keywords:
 - D3D12DDICAPS_TYPE_VIDEO_0020
 - d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDICAPS_TYPE_VIDEO_0020
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDICAPS_TYPE_VIDEO_0020 enumeration

## -description

A **D3D12DDICAPS_TYPE_VIDEO_0020** enumeration value specifies a *video feature* or a *video feature set* to [query about](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md).

## -enum-fields

### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT:0

Check if a video decode profile, bitstream encryption, resolution, and format are supported. The result is a [D3D12DDI_VIDEO_DECODE_TIER_0020](ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md) that indicates the level of support. The associated structure is [D3D12DDI_VIDEO_DECODE_SUPPORT_DATA](../d3d12umddi/ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES:1

Retrieve the list of video decode profiles supported by the adapter. The associated structure is [D3D12DDI_VIDEO_DECODE_PROFILES_DATA](ns-d3d12umddi-d3d12ddi_video_decode_profiles_data_0020.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS:2

Retrieve the list of video decode formats supported by the adapter. The associated structure is [D3D12DDI_VIDEO_DECODE_CONFIGURATION](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md) structure.

### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT:3

Check whether a color space conversion, format conversion, and scale are supported. The associated structure is [D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA](ns-d3d12umddi-d3d12ddi_video_decode_conversion_support_data_0032.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES:4

Retrieve the list of bitstream encryption schemes that are supported by the adapter. The associated structure is [D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA](ns-d3d12umddi-d3d12ddi_video_decode_bitstream_encryption_schemes_data_0020.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT:5

Retrieve the video processor capabilities. The associated structure is [D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA](ns-d3d12umddi-d3d12ddi_video_process_support_data_0032.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS:6

Retrieve the maximum number of input video streams that can be enabled at the same time. The associated structure is [D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA](ns-d3d12umddi-d3d12ddi_video_process_max_input_streams_data_0020.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO:7

Retrieve the number of past and future frames required for a given de-interlace mode, filters, frame rate conversion, and features. The associated structure is [D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA](ns-d3d12umddi-d3d12ddi_video_process_reference_info_data_0020.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE:8

Retrieve the video decoder heap size. The size of the video decoder heap is static at compile time. The associated structure is [D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033](ns-d3d12umddi-d3d12ddi_video_decoder_heap_size_data_0033.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_PROCESSOR_SIZE:9

Retrieve the video decoder processor size. The associated structure is [D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0032](ns-d3d12umddi-d3d12ddi_video_processor_size_data_0032.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_PROFILE_COUNT:10

Retrieve the number of profiles supported by the video decoder. The associated structure is [D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA](ns-d3d12umddi-d3d12ddi_video_decode_profile_count_data_0032.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_FORMAT_COUNT:11

Retrieve the number of formats supported by the video decoder. The associated structure is [D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA](ns-d3d12umddi-d3d12ddi_video_decode_format_count_data_0032.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT:12

Retrieve the number of bitstream encryption schemes suppoorted by the video decoder. The associated structure is [D3D12DDI_VIDEO_ DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA](ns-d3d12umddi-d3d12ddi_video_decode_bitstream_encryption_schemes_data_0020.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_SUPPORT:13

Retrieve the video crypto session capabilities. The associated structure is [D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_crypto_session_support_data_0030.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_COUNT:14

Retrieve the video content protection system count. The associated structure is [D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_COUNT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_content_protection_system_count_data_0030.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_SUPPORT:15

Retrieve the video content protection system support. The associated structure is [D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_content_protection_system_support_data_0030.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_TRANSFORM_SUPPORT:16

Retrieve the video crypto session transform support. The associated structure is [D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030](ns-d3d12umddi-d3d12ddi_video_crypto_session_transform_support_data_0030.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0040_DECODE_HISTOGRAM:18

Retrieve the video decode histogram data. The associated structure is [D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041](ns-d3d12umddi-d3d12ddi_video_decode_histogram_data_0041.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0053_FEATURE_AREA_SUPPORT:19

Retrieve the video feature support provided, such as whether the device provides support for video decoding, video processing, and/or video encoding. The associated structure is [D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053](ns-d3d12umddi-d3d12ddi_video_feature_area_support_data_0053.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR:20

Retrieve the supported capabilities for video motion estimation. The associated structure is [D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060](ns-d3d12umddi-d3d12ddi_video_motion_estimator_data_0060.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR_SIZE:21

Retrieve the allocated size of a video motion estimator heap. The associated structure is [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0060](ns-d3d12umddi-d3d12ddi_video_motion_estimator_size_data_0060.md).

### -field D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_COUNT:22

Retrieve the number of supported video extension commands. The associated structure is [D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_command_count_data_0063.md).

Available starting in Windows 10, version 1903 (WDDM 2.6)

### -field D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS:23

Retrieve the list of video extension commands. The associated structure is [D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_commands_data_0063.md).

Available starting in Windows 10, version 1903 (WDDM 2.6).

### -field D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETER_COUNT:24

Retrieve the number of parameters for a parameter stage. The associated structure is [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_COUNT_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_command_parameter_count_data_0063.md).

Available starting in Windows 10, version 1903 (WDDM 2.6).

### -field D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS:25

Retrieve the list of [parameter info structures](ns-d3d12umddi-d3d12ddi_video_extension_command_parameter_info_0063.md) that describe video extension command parameters for a parameter stage. The associated structure is [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETERS_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_command_parameters_data_0063.md).

Available starting in Windows 10, version 1903 (WDDM 2.6).

### -field D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_CAPS:26

Retrieve the capabilities of a particular video extension command. The associated structure is [D3D12DDI_VIDEO_EXTENSION_COMMAND_CAPS_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_command_caps_data_0063.md).

Available starting in Windows 10, version 1903 (WDDM 2.6).

### -field D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_SIZE:27

Retrieve the allocation size of a video extension command. The associated structure is [D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_command_size_data_0063.md).

Available starting in Windows 10, version 1903 (WDDM 2.6).

### -field D3D12DDICAPS_TYPE_VIDEO_0072_DECODE_PROTECTED_RESOURCES:28

Retrieve the video decode protected resource support capabilities. The associated structure is [**D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072**](ns-d3d12umddi-d3d12ddi_video_decode_protected_resources_data_0072.md).

Available starting in Windows 10, version 2004 (WDDM 2.8).

### -field D3D12DDICAPS_TYPE_VIDEO_0072_PROCESS_PROTECTED_RESOURCES:29

Retrieve the video process protected resource support capabilities. The associated structure is [**D3D12DDI_VIDEO_PROCESS_PROTECTED_RESOURCES_DATA_0072**](ns-d3d12umddi-d3d12ddi_video_decode_protected_resources_data_0072.md).

Available starting in Windows 10, version 2004 (WDDM 2.8).

### -field D3D12DDICAPS_TYPE_VIDEO_0072_MOTION_ESTIMATOR_PROTECTED_RESOURCES:30

Retrieve the video motion estimator protected resource support capabilities. The associated structure is [**D3D12DDI_VIDEO_DECODE_PROTECTED_RESOURCES_DATA_0072**](ns-d3d12umddi-d3d12ddi_video_decode_protected_resources_data_0072.md).

Available starting in Windows 10, version 2004 (WDDM 2.8).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_CODEC:31

Check whether the adapter supports the specified codec for video encoding. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_CODEC_DATA_0080](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_data_0080.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_PROFILE_LEVEL:32

Check whether the adapter supports the specified profile for video encoding and return the supported levels range for that profile. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_profile_level_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_OUTPUT_RESOLUTION_RATIOS_COUNT:33

Retrieve the number of supported resolution ratios for the specified codec configuration. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_OUTPUT_RESOLUTION_RATIOS_COUNT_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_output_resolution_ratios_count_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_OUTPUT_RESOLUTION:34

Retrieve the resolution support rules of the specified codec. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_OUTPUT_RESOLUTION_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_output_resolution_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_INPUT_FORMAT:35

Check whether a specified video encoding input format is supported. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_input_format_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_RATE_CONTROL_MODE:36

Check whether a specified video encoding rate control mode is supported. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_RATE_CONTROL_MODE_DATA_0080](ns-d3d12umddi-d3d12ddicaps_video_encoder_rate_control_mode_data_0080.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_INTRA_REFRESH_MODE:37

Check whether a specified video encoding intra refresh mode is supported. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_INTRA_REFRESH_MODE_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_intra_refresh_mode_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_FRAME_SUBREGION_LAYOUT_MODE:38

Check whether a specified frame subregion layout mode is supported. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_frame_subregion_layout_mode_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_HEAP_SIZE:39

Retrieve the memory requirements of a video encoder heap with the specified encoder heap properties. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_heap_size_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_CODEC_CONFIGURATION_SUPPORT:40

Retrieve a set of codec specific configuration limits. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0083_0](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_configuration_support_data_0083_0.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_SUPPORT:41

Retrieve the feature support details for the requested configuration. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT:42

Retrieve the codec-specific capabilities related to the reference picture management limitations. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_picture_control_support_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

### -field D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_RESOURCE_REQUIREMENTS:43

Retrieve the alignment requirements for resource access. The associated structure is [D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2](ns-d3d12umddi-d3d12ddicaps_video_encoder_resource_requirements_data_0080_2.md).

Available starting in Windows 11 (WDDM 3.0).

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)

[**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md)
