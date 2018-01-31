---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_GETCAPS_0020
title: D3D12DDIARG_VIDEO_GETCAPS_0020
author: windows-driver-content
description: Specifies values used to get capabilities of a type.
old-location: display\d3d12ddiarg_video_getcaps.htm
old-project: display
ms.assetid: 3C55B67F-043A-4747-A44A-A162D6391003
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDIARG_VIDEO_GETCAPS_0020, display.d3d12ddiarg_video_getcaps, D3D12DDIARG_VIDEO_GETCAPS_0020, D3D12DDIARG_VIDEO_GETCAPS_0020 structure [Display Devices]
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
-	D3D12DDIARG_VIDEO_GETCAPS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_VIDEO_GETCAPS_0020
---

# D3D12DDIARG_VIDEO_GETCAPS_0020 structure


## -description


Specifies values used to get capabilities of a type. 


## -syntax


````
typedef struct D3D12DDIARG_VIDEO_GETCAPS {
  D3D12DDICAPS_TYPE_VIDEO_0020 Type;
  VOID                         *pInfo;
  VOID                         *pData;
  UINT                         DataSize;
} D3D12DDIARG_VIDEO_GETCAPS_0020;
````


## -struct-fields




#### - Type

A type. 


#### - pInfo

A pointer to a memory block that contains data that specifies the condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.


#### - pData

A pointer to a memory block that contains capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition specified by the <b>pInfo</b> member. 


#### - DataSize

The size, in bytes, of the data at <b>pData</b>.

