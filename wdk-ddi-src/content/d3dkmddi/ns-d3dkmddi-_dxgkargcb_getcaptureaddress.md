---
UID: NS:d3dkmddi._DXGKARGCB_GETCAPTUREADDRESS
title: _DXGKARGCB_GETCAPTUREADDRESS (d3dkmddi.h)
description: The DXGKARGCB_GETCAPTUREADDRESS structure describes parameters for retrieving information about a capture buffer that is associated with an allocation.
old-location: display\dxgkargcb_getcaptureaddress.htm
ms.assetid: 95f1bbf4-06d8-48b7-a983-bf0b65ec2da3
ms.date: 05/10/2018
ms.keywords: "*INOUT_PDXGKARGCB_GETCAPTUREADDRESS, DXGKARGCB_GETCAPTUREADDRESS, DXGKARGCB_GETCAPTUREADDRESS structure [Display Devices], DmStructs_24ed27a0-7ad3-44d1-aa93-c22733ebfb34.xml, _DXGKARGCB_GETCAPTUREADDRESS, d3dkmddi/DXGKARGCB_GETCAPTUREADDRESS, display.dxgkargcb_getcaptureaddress"
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARGCB_GETCAPTUREADDRESS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKARGCB_GETCAPTUREADDRESS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_GETCAPTUREADDRESS
---

# _DXGKARGCB_GETCAPTUREADDRESS structure


## -description


The DXGKARGCB_GETCAPTUREADDRESS structure describes parameters for retrieving information about a capture buffer that is associated with an allocation.


## -struct-fields




### -field hAllocation

[in] A handle to the allocation that is associated with the capture buffer to retrieve information on. 


### -field SegmentId

[out] The identifier of the segment for the capture buffer. The allocation that is associated with the capture buffer is currently paged in this segment.


### -field PhysicalAddress

[out] The physical address of the capture buffer.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_getcaptureaddress">DxgkCbGetCaptureAddress</a>
 

 

