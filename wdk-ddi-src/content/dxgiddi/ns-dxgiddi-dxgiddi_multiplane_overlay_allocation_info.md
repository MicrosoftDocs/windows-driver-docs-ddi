---
UID: NS:dxgiddi.DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
title: DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO (dxgiddi.h)
description: Specifies info about a multiplane overlay allocation.
old-location: display\dxgiddi_multiplane_overlay_allocation_info.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure"]
ms.keywords: DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO, DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure [Display Devices], display.dxgiddi_multiplane_overlay_allocation_info, dxgiddi/DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
f1_keywords:
 - DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
 - dxgiddi/DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
---

# DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure


## -description

Specifies info about a multiplane overlay allocation.

## -struct-fields

### -field PresentAllocation

[in] A handle to the multiplane overlay allocation.

### -field SubResourceIndex

[in] The zero-based index into the resource which the handle in the <b>PresentAllocation</b> member specifies. This index indicates the display surface.

