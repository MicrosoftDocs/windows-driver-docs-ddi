---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GETCAPS
title: PFND3D12DDI_VIDEO_GETCAPS (d3d12umddi.h)
description: The pfnGetCaps callback function defines an entry point for video specific caps.
old-location: display\pfnd3d12ddi_video_getcaps.htm
ms.assetid: 6875B754-115F-481D-8D46-2A383BA6B5E7
ms.date: 04/16/2018
ms.keywords: PFND3D12DDI_VIDEO_GETCAPS, PFND3D12DDI_VIDEO_GETCAPS callback, d3d12umddi/pfnGetCaps, display.pfnd3d12ddi_video_getcaps, pfnGetCaps, pfnGetCaps callback function [Display Devices]
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
req.typenames: 
f1_keywords:
 - "d3d12umddi/pfnGetCaps"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - pfnGetCaps
product:
 - Windows
---

# PFND3D12DDI_VIDEO_GETCAPS callback function

## -description

The <i>pfnGetCaps</i> callback function defines an entry point for video specific capabilities.

## -parameters

### -param hDrvDevice

The handle of a device.

### -param pArgs

[in] Values used to get capabilities.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

Access this function though the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020">D3D12DDI_VIDEO_DECODE_SUPPORT_DATA</a> structure.

The following list describes the mapping of D3D12DDICAPS_TYPE_VIDEO_0010 type to the meaning of the pInfo, pData, and DataSize parameters.

D3D12DDICAPS_TYPE_VIDEO_DECODE_SUPPORT

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_DECODE_SUPPORT_DATA*|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_SUPPORT_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILES

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_DECODE_PROFILES_DATA*|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_PROFILES_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_FORMATS

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_DECODE_FORMATS_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_FORMATS_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA*|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_PROCESS_SUPPORT

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA*|
|DataSize|sizeof(D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_PROCESS_MAX_INPUT_STREAMS

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_PROCESS_REFERENCE_INFO

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_COUNT

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_ DECODE_PROFILE_COUNT_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_FORMAT_COUNT

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_ DECODE_PROFILE_FORMAT_COUNT_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_PROFILE_FORMAT_COUNT_DATA)|
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT

|Member|Value|
|--- |--- |
|pInfo|nullptr|
|pData|D3D12DDI_VIDEO_ DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA *|
|DataSize|sizeof(D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA)|

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020">D3D12DDI_VIDEO_DECODE_SUPPORT_DATA</a>

