---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
title: D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
author: windows-driver-content
description: Contains the reference frames needed to perform video processing.
old-location: display\d3d12ddi_video_process_references_info.htm
old-project: display
ms.assetid: 63DB66FB-E02B-4C5E-AC7A-654E9D70435A
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 structure [Display Devices], D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020, display.d3d12ddi_video_process_references_info
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
-	D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
---

# D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 structure


## -description


Contains the reference frames needed to perform video processing.


## -syntax


````
typedef struct D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 {
  UINT               NumPastFrames;
  D3D12DDI_HRESOURCE *hDrvPastFrames;
  UINT               *pPastSubresources;
  UINT               NumFutureFrames;
  D3D12DDI_HRESOURCE *hDrvFutureFrames;
  UINT               *pFutureSubresources;
} D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020;
````


## -struct-fields




### -field NumPastFrames

The number of past reference frames.



### -field hDrvPastFrames

A pointer to an array of surfaces. The number of elements in the array is the value of the <i>NumPastFrames</i> parameter.


### -field pPastSubresources

An array of subresource indexes for the list of past frames textures.  A value of null indicates subresource of zero (0) for each resource.


### -field NumFutureFrames

The number of future reference frames.


### -field hDrvFutureFrames

A pointer to an array of surfaces. The number of elements in the array is the value of  <i>NumFutureFrames</i> parameter.


### -field pFutureSubresources

An array of subresource indexes for the list of future frames textures.  A value of null indicates subresource 0 for each resource.

