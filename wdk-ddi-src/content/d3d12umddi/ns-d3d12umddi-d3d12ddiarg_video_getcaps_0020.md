---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_GETCAPS_0020
title: D3D12DDIARG_VIDEO_GETCAPS_0020
author: windows-driver-content
description: Specifies values used to get capabilities of a type.
old-location: display\d3d12ddiarg_video_getcaps.htm
ms.assetid: 3C55B67F-043A-4747-A44A-A162D6391003
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDIARG_VIDEO_GETCAPS_0020, D3D12DDIARG_VIDEO_GETCAPS_0020 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_GETCAPS_0020, display.d3d12ddiarg_video_getcaps
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDIARG_VIDEO_GETCAPS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_VIDEO_GETCAPS_0020
---

# D3D12DDIARG_VIDEO_GETCAPS_0020 structure


## -description


Specifies values used to get capabilities of a type, in the call to [PFND3D12DDI_VIDEO_GETCAPS](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md).


## -struct-fields




### -field Type

A type, specified by a pointer to [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).


### -field pInfo

A pointer to a memory block that contains data that specifies the condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.


### -field pData

A pointer to a memory block that contains capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition specified by the <b>pInfo</b> member.


### -field DataSize

The size, in bytes, of the memory block at <b>pData</b>.

