---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032
description: Video decode profile count data.
old-location: display\d3d12ddi-video-decode-profile-count-data-0032.htm
ms.assetid: 8398579d-e8cf-4c58-ac74-eeddf2dca23b
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032, display.d3d12ddi-video-decode-profile-count-data-0032
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032 structure


## -description


Retrieve the count of decode profiles supported by the driver.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field ProfileCount

The count of decoder profiles supported by driver.

