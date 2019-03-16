---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020
title: D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020 (d3d12umddi.h)
description: Defines the layout in memory of a stereo 3D video frame.
old-location: display\d3d12ddi_video_frame_stereo_format.htm
ms.assetid: 91C5C387-320C-4ABE-98AB-36D2CDE7428F
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020, D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020 enumeration [Display Devices], D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_HORIZONTAL, D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_MONO, D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_SEPARATE, D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_VERTICAL, d3d12umddi/D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020, d3d12umddi/D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_HORIZONTAL, d3d12umddi/D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_MONO, d3d12umddi/D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_SEPARATE, d3d12umddi/D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_VERTICAL, display.d3d12ddi_video_frame_stereo_format
ms.topic: enum
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
- D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020
---

# D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020 enumeration


## -description


Defines the layout in memory of a stereo 3D video frame.

## -enum-fields




### -field D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_MONO

The sample does not contain stereo data. If the stereo format is not specified, this value is the default.


### -field D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_HORIZONTAL

Frame 0 and frame 1 are packed side-by-side, as shown in the following diagram:

<table>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
</table>
 


### -field D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_VERTICAL

Frame 0 and frame 1 are packed top-to-bottom, as shown in the following diagram:

<table>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
</table>
 


### -field D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020_SEPARATE

Frame 0 and frame 1 are placed in separate resources.


## -remarks



All drivers that support stereo must support all the formats in this enumeration.



