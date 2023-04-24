---
UID: NS:ksmedia.tagKS_H264VIDEOINFO
title: KS_H264VIDEOINFO (ksmedia.h)
description: The KS_H264VIDEOINFO describes the device capabilities that apply to the current media type.
tech.root: stream
ms.date: 01/04/2023
keywords: ["tagKS_H264VIDEOINFO structure"]
ms.keywords: "*PKS_H264VIDEOINFO, KS_H264VIDEOINFO, KS_H264VIDEOINFO structure [Streaming Media Devices], PKS_H264VIDEOINFO, PKS_H264VIDEOINFO structure pointer [Streaming Media Devices], ksmedia/KS_H264VIDEOINFO, ksmedia/PKS_H264VIDEOINFO, stream.ks_h264videoinfo, tagKS_H264VIDEOINFO"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: KS_H264VIDEOINFO, *PKS_H264VIDEOINFO
f1_keywords:
 - tagKS_H264VIDEOINFO
 - ksmedia/tagKS_H264VIDEOINFO
 - PKS_H264VIDEOINFO
 - ksmedia/PKS_H264VIDEOINFO
 - KS_H264VIDEOINFO
 - ksmedia/KS_H264VIDEOINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - tagKS_H264VIDEOINFO
 - PKS_H264VIDEOINFO
 - KS_H264VIDEOINFO
---

## -description

The **KS_H264VIDEOINFO** describes the device capabilities that apply to the current media type.

## -struct-fields

### -field wWidth

Specifies the width in pixels of pictures output from the decoding process.

The value for this member must be a multiple of 2, but it does not have to be an integer multiple of 16. It can be specified using a frame cropping rectangle in the active Sequence Parameter Set (SPS).

### -field wHeight

Specifies the height in pixels of pictures output from the decoding process.

The value for this member must be a multiple of 2. When field coding or frame/field adaptive coding is used, it must be a multiple of 4. It does not have to be an integer multiple of 16. It can be specified using a frame cropping rectangle in the active SPS.

### -field wSARwidth

Specifies the sample aspect ratio width as defined in the H.264 Annex E.

It must  be relatively prime with respect to **wSARheight**.

### -field wSARheight

Specifies the sample aspect ratio height as defined in the H.264 Annex E.

It must be relatively prime with respect to **bSARwidth**.

### -field wProfile

Specifies the first two bytes of the sequence parameter set as described by profile_idc and constraint flags in the H.264 specification.

This member indicates the profile and applicable constraints to be used.

The following are examples of allowed values:

| Value | Description |
|--|--|
| 0x4240 | Constrained Baseline Profile. |
| 0x4200 | Baseline Profile. |
| 0x4D00 | Main Profile. |
| 0x6400 | High Profile. |
| 0x5300 | Scalable Baseline Profile. |
| 0x5600 | Scalable High Profile. |
| 0x7600 | Multiview High Profile. |
| 0x8000 | Stereo High Profile. |

### -field bLevelIDC

Specifies the level as described by the level_idc flag.

This member indicates the minimum level that supports the resolution and the maximum bit rate for this frame descriptor.

The following are examples of allowed values:

| Value | Description |
|--|--|
| 0x1F | Level 3.1. |
| 0x28 | Level 4.0. |

### -field wConstrainedToolset

Constrains the features allowed by **wProfile**.

| Value | Description |
|--|--|
| 0 | No constraints. All tools defined by the selected **wProfile** and the bmSetting set are allowed. |
| 1 | Unified Communication (UC) Constrained High Toolset. |
| 2 | UC Scalable Constrained High1. |
| 3 | UC Scalable Constrained Baseline1. |
| 4 to 65535 | Reserved. |

### -field bmSupportedUsages

Defines the bitmap that specifies the supported usages.

| Bits | Description |
|--|--|
| D0 | Real-time/UCConfig (Unified Communication Configuration) mode 0. |
| D1 | Real-time/UCConfig mode 1. |
| D2 | Real-time/UCConfig mode 2Q. |
| D3 | Real-time/UCConfig mode 2S. |
| D4 | Real-time/UCConfig mode 3. |
| D7-D5 | Reserved; set to 0. |
| D15-D8 | Broadcast modes. |
| D16 | File storage mode with I and P slices (for example, IPPP). |
| D17 | File storage mode with I, P and B slices (for example, IB...IP). |
| D18 | File storage all-I-frame mode. |
| D23-D19 | Reserved; set to 0. |
| D24 | MVC Stereo High Mode. |
| D25 | MVC Multiview Mode. |
| D31-D26 | Reserved; set to 0. |

### -field bmCapabilities

Defines the bitmap that specifies the capabilities for this frame descriptor.

| Bits | Description |
|--|--|
| D0 | Context based Adaptive Variable Length Coding (CAVLC ) only. |
| D1 | Context based Adaptive Binary Arithmetic Coding (CABAC) only. |
| D2 | Constant frame rate. |
| D3 | Separate QP for luma/chroma. |
| D4 | Separate QP for Cb/Cr. |
| D5 | No picture reordering. |
| D15-D6 | Reserved; set to 0. |

### -field bmSVCCapabilities

Defines the bitmap that specifies the Scalable Video Coding (SVC) capabilities.

| Bits | Description |
|--|--|
| D2-D0 | Maximum number of temporal layers minus 1. |
| D3 | Rewrite support. |
| D6-D4 | Maximum number of Coarse Grained Scalability (CGS) layers minus 1. |
| D9-D7 | Maximum number of Medium Grained Scalability (MGS) sublayers. |
| D10 | Additional SNR scalability support in spatial enhancement layers. |
| D13-D11 | Maximum number of spatial layers minus 1. |
| D31-D14 | Reserved. |

### -field bmMVCCapabilities

Defines the bitmap that specifies the Multicast Video Coding (MVC) capabilities.

| Bits | Description |
|--|--|
| D2-D0 | Maximum number of temporal layers minus 1. |
| D11-D3 | Maximum number of view components minus 1. |
| D31-D11 | Reserved. |

### -field dwFrameInterval

Specifies the supported frame interval.

This is the shortest frame interval supported, at the highest frame rate, in 100-nanoseconds units.

### -field bMaxCodecConfigDelay

Specifies the maximum number of frames the encoder takes to respond to a command.

### -field bmSupportedSliceModes

Defines the bitmap that specifies the slice modes.

| Bits | Description |
|--|--|
| D0 | Slice mode 0. |
| D1 | Slice mode 1. |
| D7-D2 | Reserved. |

### -field bmSupportedSyncFrameTypes

Defines the **BYTE** member **bmSupportedSyncFrameTypes**.

### -field bResolutionScaling

Defines the bitmap that specifies the synchronization frame types.

| Bits | Description |
|--|--|
| D0 | Instantaneous Decoding Refresh (IDR) frame with Sequence Parameter Set (SPS) and Picture Parameter Set (PPS) headers. |
| D1 | IDR frame (with SPS and PPS headers) that is a long term reference frame. |
| D2 | Random-access I frame (with SPS and PPS headers), which may or may not be an IDR frame. |
| D3 | P frame that is a long term reference frame. |
| D7-D4 | Reserved; set to 0. |

### -field bSimulcastSupport

Specifies the number of H.264 video streaming endpoints and the number of streams this endpoint supports.

| Value | Description |
|--|--|
| 0 | One endpoint and one stream. |
| 1 | One endpoint and multiple streams. |

### -field bmSupportedRateControlModes

Defines the bitmap that specifies the rate control modes.

| Bits | Description |
|--|--|
| D0 | Variable bit rate (VBR) with underflow allowed (H.264 low_delay_hrd_flag = 1). |
| D1 | Constant bit rate (CBR) (H.264 low_delay_hrd_flag = 0). |
| D2 | Constant QP. |
| D3 | Global VBR with underflow allowed (H.264 low_delay_hrd_flag = 1). |
| D4 | VBR without underflow (H.264 low_delay_hrd_flag = 0). |
| D5 | Global VBR without underflow (H.264 low_delay_hrd_flag = 0). |
| D7-D6 | Reserved, set to 0. |

### -field wMaxMBperSecOneResolutionNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable Advanced Video Coding (AVC) streams, summing up across all layers when all layers have the same resolution.

### -field wMaxMBperSecTwoResolutionsNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable AVC streams, summing up across all layers when all layers consist of two different resolutions.

### -field wMaxMBperSecThreeResolutionsNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable AVC streams, summing up across all layers when all layers consist of three different resolutions.

### -field wMaxMBperSecFourResolutionsNoScalability

Specifies the maximum macroblock processing rate allowed for non-scalable AVC streams, summing up across all layers when all layers consist of four different resolutions.

### -field wMaxMBperSecOneResolutionTemporalScalability

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers have the same resolution.

### -field wMaxMBperSecTwoResolutionsTemporalScalablility

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers consist of two different resolutions.

### -field wMaxMBperSecThreeResolutionsTemporalScalability

Specifies the maximum macroblock processing rate allowed for temporal scalable streams, summing up across all layers when all layers consist of three different resolutions.

### -field wMaxMBperSecFourResolutionsTemporalScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of four different resolutions.

### -field wMaxMBperSecOneResolutionTemporalQualityScalability

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers have the same resolution.

### -field wMaxMBperSecTwoResolutionsTemporalQualityScalability

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers consist of two different resolutions.

### -field wMaxMBperSecThreeResolutionsTemporalQualityScalablity

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers consist of three different resolutions.

### -field wMaxMBperSecFourResolutionsTemporalQualityScalability

Specifies the maximum macroblock processing rate allowed for temporal and quality scalable SVC streams, summing up across all layers when all layers consist of four different resolutions.

### -field wMaxMBperSecOneResolutionTemporalSpatialScalability

Defines the **WORD** member **wMaxMBperSecOneResolutionTemporalSpatialScalability**.

### -field wMaxMBperSecTwoResolutionsTemporalSpatialScalability

Defines the **WORD** member **wMaxMBperSecTwoResolutionsTemporalSpatialScalability**.

### -field wMaxMBperSecThreeResolutionsTemporalSpatialScalablity

Defines the **WORD** member **wMaxMBperSecThreeResolutionsTemporalSpatialScalablity**.

### -field wMaxMBperSecFourResolutionsTemporalSpatialScalability

Defines the **WORD** member **wMaxMBperSecFourResolutionsTemporalSpatialScalability**.

### -field wMaxMBperSecOneResolutionFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers have the same resolution.

### -field wMaxMBperSecTwoResolutionsFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of two different resolutions.

### -field wMaxMBperSecThreeResolutionsFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of three different resolutions.

### -field wMaxMBperSecFourResolutionsFullScalability

Specifies the maximum macroblock processing rate allowed for fully scalable streams, summing up across all layers when all layers consist of four different resolutions.

## -remarks

The KS_H264VIDEOINFO structure contains the frame and the format descriptor information.

## -see-also

[KS_DATAFORMAT_H264VIDEOINFO](./ns-ksmedia-tagks_dataformat_h264videoinfo.md)

[KS_DATARANGE_H264_VIDEO](./ns-ksmedia-tagks_datarange_h264_video.md)
