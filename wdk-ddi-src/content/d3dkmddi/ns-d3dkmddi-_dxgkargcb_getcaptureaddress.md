---
UID: NS:d3dkmddi._DXGKARGCB_GETCAPTUREADDRESS
title: DXGKARGCB_GETCAPTUREADDRESS (d3dkmddi.h)
description: The DXGKARGCB_GETCAPTUREADDRESS structure describes parameters for retrieving information about a capture buffer that is associated with an allocation.
old-location: display\dxgkargcb_getcaptureaddress.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_GETCAPTUREADDRESS structure"]
ms.keywords: "*INOUT_PDXGKARGCB_GETCAPTUREADDRESS, DXGKARGCB_GETCAPTUREADDRESS, DXGKARGCB_GETCAPTUREADDRESS structure [Display Devices], DmStructs_24ed27a0-7ad3-44d1-aa93-c22733ebfb34.xml, _DXGKARGCB_GETCAPTUREADDRESS, d3dkmddi/DXGKARGCB_GETCAPTUREADDRESS, display.dxgkargcb_getcaptureaddress"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_GETCAPTUREADDRESS
f1_keywords:
 - _DXGKARGCB_GETCAPTUREADDRESS
 - d3dkmddi/_DXGKARGCB_GETCAPTUREADDRESS
 - DXGKARGCB_GETCAPTUREADDRESS
 - d3dkmddi/DXGKARGCB_GETCAPTUREADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_GETCAPTUREADDRESS
 - DXGKARGCB_GETCAPTUREADDRESS
---

# DXGKARGCB_GETCAPTUREADDRESS structure

## -description

The **DXGKARGCB_GETCAPTUREADDRESS** structure contains the arguments used in the [**DXGKCB_GETCAPTUREADDRESS**](nc-d3dkmddi-dxgkcb_getcaptureaddress.md) callback function, to retrieve information about a capture buffer that is associated with an allocation.

## -struct-fields

### -field hAllocation

[in] A handle to the allocation that is associated with the capture buffer to retrieve information on.

### -field SegmentId

[out] The identifier of the segment for the capture buffer. The allocation that is associated with the capture buffer is currently paged in this segment.

### -field PhysicalAddress

[out] The physical address of the capture buffer.

## -see-also

[**DXGKCB_GETCAPTUREADDRESS**](nc-d3dkmddi-dxgkcb_getcaptureaddress.md)
