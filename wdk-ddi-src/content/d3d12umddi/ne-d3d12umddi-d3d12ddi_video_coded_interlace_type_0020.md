---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
title: D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 (d3d12umddi.h)
description: Indicates whether the compressed stream contains only frames (PROGRESSIVE_ONLY) or may contain a mix of progressive and interlaced frames (FIELDS).
old-location: display\d3d12ddi_video_coded_interlace_type.htm
ms.assetid: 5440595D-C692-4349-9332-393CCB11DBFF
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020, D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 enumeration [Display Devices], D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED, D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020, d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED, d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE, display.d3d12ddi_video_coded_interlace_type
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020
---

# D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 enumeration


## -description


Indicates whether the compressed stream contains only frames (PROGRESSIVE_ONLY) or may contain a mix of progressive and interlaced frames (FIELDS).


## -enum-fields




### -field D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_NONE

The coded video stream contains only progressive frames.


### -field D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020_FIELD_BASED

The coded video stream may contain a mix of progressive and interlaced frames.

## -remarks

With H.264 for instance, D3D12DDI_VIDEO_CODED_TYPE_FIELDS is used for both PAFF (picture adaptive frame field) and MBAFF (macroblock-level adaptive frame/field).
