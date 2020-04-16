---
UID: NE:d3dukmdt._D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
title: _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING (d3dukmdt.h)
description: The D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration is used to indicate the scan line ordering of a video output signal.
old-location: display\d3dddi_video_signal_scanline_ordering.htm
tech.root: display
ms.assetid: f0dcfd93-1706-41f7-aab5-f9e9dd58e9b3
ms.date: 05/10/2018
keywords: ["_D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration"]
ms.keywords: D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING, D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration [Display Devices], D3DDDI_VSSLO_INTERLACED_LOWERFIELDFIRST, D3DDDI_VSSLO_INTERLACED_UPPERFIELDFIRST, D3DDDI_VSSLO_OTHER, D3DDDI_VSSLO_PROGRESSIVE, D3DDDI_VSSLO_UNINITIALIZED, DmEnums_81ac5c85-97c5-40ac-a6e6-df079576211a.xml, _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING, d3dukmdt/D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING, d3dukmdt/D3DDDI_VSSLO_INTERLACED_LOWERFIELDFIRST, d3dukmdt/D3DDDI_VSSLO_INTERLACED_UPPERFIELDFIRST, d3dukmdt/D3DDDI_VSSLO_OTHER, d3dukmdt/D3DDDI_VSSLO_PROGRESSIVE, d3dukmdt/D3DDDI_VSSLO_UNINITIALIZED, display.d3dddi_video_signal_scanline_ordering
f1_keywords:
 - "d3dukmdt/D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING"
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dukmdt.h
api_name:
- D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
---

# _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration


## -description


The D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration is used to indicate the scan line ordering of a video output signal.  


## -enum-fields




### -field D3DDDI_VSSLO_UNINITIALIZED

Indicates that a variable of type D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING has not yet been assigned a meaningful value.


### -field D3DDDI_VSSLO_PROGRESSIVE

Indicates that each field contains an entire frame.


### -field D3DDDI_VSSLO_INTERLACED_UPPERFIELDFIRST

Indicates that each field contains half of a frame, and the odd scan lines are displayed first. 


### -field D3DDDI_VSSLO_INTERLACED_LOWERFIELDFIRST

Indicates that each field contains half of a frame, and the even scan lines are displayed first. 


### -field D3DDDI_VSSLO_OTHER

Indicates that the video signal has a scan line ordering other than those given in the previous constants of this enumeration.


## -remarks



The values of the D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration type indicate whether the image displayed on the monitor contains the entire content of a video frame or only half of the content (that is, either the even or odd scan lines, which occur interchangeably). The values also indicate which field comes first in the ordering.



