---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
title: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
author: windows-driver-content
description: Data structure for D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check. Retrieves the number of past and future frames required for a given deinterlace mode.
old-location: display\d3d12ddi_video_process_reference_info_data.htm
old-project: display
ms.assetid: 3711ACBD-482E-4BB8-8530-C92DA610CA5B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020, D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure [Display Devices], display.d3d12ddi_video_process_reference_info_data
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
---

# D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure


## -description


Data structure for D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check.  Retrieves the number of past and future frames required for a given deinterlace mode.


## -syntax


````
typedef struct D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 {
  UINT                                              NodeIndex;
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020     DeinterlaceMode;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020          Filters;
  D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS_0020 FeatureSupport;
  DXGI_RATIONAL                                     InputRate;
  DXGI_RATIONAL                                     OutputRate;
  BOOL                                              EnableAutoProcessing;
  UINT                                              PastFrames;
  UINT                                              FutureFrames;
} D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020;
````


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field DeinterlaceMode

The deinterlacing mode for which to retrieve the number of past and future frames.  Only a single mode may be queried at once.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.


### -field Filters

The filters for which to retrieve the number of past and future frames.  You can specify multiple filters may be specified.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.


### -field FeatureSupport

The features for which to retrieve the number of past and future frames.  For more information, see the  <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a> enumeration. 


### -field InputFrameRate

 


### -field OutputFrameRate

 


### -field EnableAutoProcessing

Whether automatic processing is used. 


### -field PastFrames

The number of past reference frames required to support this processing. 


### -field FutureFrames

The number of future reference frames required to support this processing.


#### - InputRate

The input rate of the stream. 


#### - OutputRate

The output rate of the stream.


## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

