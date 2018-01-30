---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
title: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
author: windows-driver-content
description: Specifies data used to determine support of hardware for a configuration.
old-location: display\d3d12ddi_video_decode_support_data.htm
old-project: display
ms.assetid: 05274F4B-0473-42BA-A382-B348A85DBFA5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020, D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020, display.d3d12ddi_video_decode_support_data
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
-	D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure


## -description


Specifies data used to determine support of hardware for a configuration. 


## -syntax


````
typedef struct D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 {
  UINT                                           NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020       Configuration;
  UINT                                           Width;
  UINT                                           Height;
  DXGI_FORMAT                                    DecodeFormat;
  DXGI_RATIONAL                                  FrameRate;
  UINT                                           BitRate;
  D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020       SupportFlags;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020 ConfigurationFlags;
  D3D12DDI_VIDEO_DECODE_TIER_0020                DecodeTier;
} D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020;
````


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field Configuration

The decode profile and bitstream encryption.  For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>.


### -field Width

The decode width of the source stream. 


### -field Height

The decode height of the source stream. 


### -field DecodeFormat

The DirectX resource data format to use as the decode format.  If no decoder conversion is specified, this format is the output format.


### -field FrameRate

The frame rate of the video format.  Used to help return performance hints in the <b>SupportFlags</b> member. A value of zero (0) means unknown.


### -field BitRate

The average bits per second data compression rate for the compressed video stream.  This is used by the driver to determine whether the video can be decoded in real time. A value of zero (0) means unknown.


### -field SupportFlags

Supported flags. For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020.md">D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS</a>.


### -field ConfigurationFlags

Configuration flags. For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS</a>.


### -field DecodeTier

The tier supported by this configuration.  For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md">D3D12DDI_VIDEO_DECODE_TIER</a>.


## -remarks


This structure is retrieved through the <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md">pfnGetCaps</a> callback function  with the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddicaps_type.md">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_SUPPORT</b>.



## -see-also

<b>D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS</b>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020.md">D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md">D3D12DDI_VIDEO_DECODE_TIER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

