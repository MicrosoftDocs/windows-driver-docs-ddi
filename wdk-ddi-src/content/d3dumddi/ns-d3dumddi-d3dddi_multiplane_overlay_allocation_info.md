---
UID: NS:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
title: D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO (d3dumddi.h)
description: Specifies info about a multiplane overlay allocation.
old-location: display\d3dddi_multiplane_allocation_info.htm
tech.root: display
ms.assetid: ce3610ab-a927-45e7-8ceb-3f38b5f50f00
ms.date: 05/10/2018
keywords: ["D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure"]
ms.keywords: D3DDDI_MULTIPLANE_ALLOCATION_INFO, D3DDDI_MULTIPLANE_ALLOCATION_INFO structure [Display Devices], D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO, d3dumddi/D3DDDI_MULTIPLANE_ALLOCATION_INFO, display.d3dddi_multiplane_allocation_info
f1_keywords:
 - "d3dumddi/D3DDDI_MULTIPLANE_ALLOCATION_INFO"
 - "D3DDDI_MULTIPLANE_ALLOCATION_INFO"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dumddi.h
api_name:
- D3DDDI_MULTIPLANE_ALLOCATION_INFO
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_ALLOCATION_INFO
---

# D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure


## -description


Specifies info about a multiplane overlay allocation.


## -struct-fields




### -field PresentAllocation

[in] A handle to the multiplane overlay allocation.


### -field SubResourceIndex

[in] The zero-based index into the resource which the handle in the <b>PresentAllocation</b> member specifies. This index indicates the display surface.

