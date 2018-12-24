---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
title: D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
description: Specifies information used to retrieve a list of profiles.
old-location: display\d3d12ddi_video_decode_profiles_data.htm
ms.assetid: D6615DE8-5103-470D-A895-6663B2CC9261
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020, D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020, display.d3d12ddi_video_decode_profiles_data
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
-	D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 structure


## -description


Specifies information used to retrieve a list of profiles.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field ProfileCount

The number of profiles to retrieve. The runtime ensures this value matches the value returned from [PFND3D12DDI_VIDEO_GETCAPS](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with D3D12DDI_CAPSTYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_COUNT.


### -field pProfiles

A pointer to the returned supported profiles. The calling application allocates storage for the profile list.


## -remarks

These capabilities allow the list of supported decode profiles supported by hardware. First, use PFND3D12DDDI_VIDEO_GETCAPS called with D3D12DDICAPS_TYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_COUNT to retrieve the number of supported profiles. The caller uses this to allocate storage to retrieve the list of profiles. Then, the list is retrieved through PFND3D12DDI_VIDEO_GETCAPS with the D3D12DDICAPS_TYPE set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILES.
