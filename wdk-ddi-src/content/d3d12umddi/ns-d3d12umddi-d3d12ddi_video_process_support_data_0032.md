---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
title: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
author: windows-driver-content
description: Video process support data.
old-location: display\d3d12ddi-video-process-support-data-0032.htm
old-project: display
ms.assetid: ea2dabc5-6853-4491-8c1f-f3f5ae516952
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 structure [Display Devices], E, I, O, P, R, S, T, U, V, _, d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032, display.d3d12ddi-video-process-support-data-0032"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
---

# D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 structure


## -description


Video process support data.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 {
  UINT                                                                               NodeIndex;
  D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020                                             InputSample;
  D3D12DDI_VIDEO_FIELD_TYPE_0020                                                     InputFieldType;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020                                            InputStereoFormat;
  DXGI_RATIONAL                                                                      InputFrameRate;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020                                             OutputFormat;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020                                            OutputStereoFormat;
  DXGI_RATIONAL                                                                      OutputFrameRate;
  D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022                                          SupportFlags;
  D3D12DDI_VIDEO_SCALE_SUPPORT_0032                                                  ScaleSupport;
  D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS_0020                                  FeatureSupport;
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020                                      DeinterlaceSupport;
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022                                  AutoProcessingSupport;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020                                           FilterSupport;
  D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020 [D3D12DDI_VIDEO_PROCESS_MAX_FILTERS_0020] FilterRangeSupport;
} D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032;
````


## -struct-fields




### -field NodeIndex

Node index.


### -field InputSample

Input sample.


### -field InputFieldType

Input field type.


### -field InputStereoFormat

Input stereo format.


### -field InputFrameRate

Input frame rate.


### -field OutputFormat

Output format.


### -field OutputStereoFormat

Output stereo format.


### -field OutputFrameRate

Output frame rate.


### -field SupportFlags

Support flags.


### -field ScaleSupport

Scale support.


### -field FeatureSupport

Feature support.


### -field DeinterlaceSupport

Deinterlace support.


### -field AutoProcessingSupport

Auto processing support.


### -field FilterSupport

Filter support.


### -field FilterRangeSupport

Filter range support.

