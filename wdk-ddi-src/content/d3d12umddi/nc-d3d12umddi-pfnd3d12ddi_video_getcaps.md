---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GETCAPS
title: PFND3D12DDI_VIDEO_GETCAPS
author: windows-driver-content
description: The pfnGetCaps callback function defines an entry point for video specific caps.
old-location: display\pfnd3d12ddi_video_getcaps.htm
old-project: display
ms.assetid: 6875B754-115F-481D-8D46-2A383BA6B5E7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_VIDEO_GETCAPS, d3d12umddi/pfnGetCaps, display.pfnd3d12ddi_video_getcaps, pfnGetCaps, pfnGetCaps callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnGetCaps
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_GETCAPS callback


## -description


The <i>pfnGetCaps</i> callback function defines an entry point for video specific caps.


## -parameters




### -param hDrvDevice

The handle of a device.


### -param *pArgs [in]

 Values used to get capabilities.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Access this function though the <a href="https://msdn.microsoft.com/05274F4B-0473-42BA-A382-B348A85DBFA5">D3D12DDI_VIDEO_DECODE_SUPPORT_DATA</a> structure.

The following list describes the mapping of D3D12DDICAPS_TYPE_VIDEO_0010 type to the meaning of the pInfo, pData, and DataSize parameters.

D3D12DDICAPS_TYPE_VIDEO_DECODE_SUPPORT

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_DECODE_SUPPORT_DATA*</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_SUPPORT_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILES

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_DECODE_PROFILES_DATA*</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_PROFILES_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_FORMATS 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_DECODE_FORMATS_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_FORMATS_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA*</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_PROCESS_SUPPORT 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA*</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_PROCESS_MAX_INPUT_STREAMS 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_PROCESS_REFERENCE_INFO 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_COUNT

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_ DECODE_PROFILE_COUNT_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_FORMAT_COUNT

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_ DECODE_PROFILE_FORMAT_COUNT_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_PROFILE_FORMAT_COUNT_DATA)</td>
</tr>
</table>
 

D3D12DDICAPS_TYPE_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>pInfo</td>
<td>nullptr</td>
</tr>
<tr>
<td>pData</td>
<td>D3D12DDI_VIDEO_ DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA *</td>
</tr>
<tr>
<td>DataSize</td>
<td>sizeof(D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA)</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/05274F4B-0473-42BA-A382-B348A85DBFA5">D3D12DDI_VIDEO_DECODE_SUPPORT_DATA</a>
 

 

