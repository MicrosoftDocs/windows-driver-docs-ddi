---
UID: NS:d3dkmthk._D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
title: _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN (d3dkmthk.h)
description: The D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure identifies a GDI present-history operation.
old-location: display\d3dkmt_gdimodel_presenthistorytoken.htm
ms.assetid: 4f602b68-7170-4e76-8875-0a0c0634caa2
ms.date: 05/10/2018
keywords: ["D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure"]
ms.keywords: D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN, D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_02351828-bca4-4a37-bb61-57224a125ee5.xml, _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN, display.d3dkmt_gdimodel_presenthistorytoken
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
f1_keywords:
 - _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
 - d3dkmthk/_D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
 - D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
 - d3dkmthk/D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN
---

# _D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure


## -description

The D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN structure identifies a GDI present-history operation.

## -struct-fields

### -field hLogicalSurface

[in] A 64-bit value that specifies the handle to a logical surface to copy from.

### -field hPhysicalSurface

[in] A 64-bit value that specifies the handle to a physical surface to copy to.

### -field ScrollRect

This member is reserved and should be set to zero.

Supported starting with Windows 8.

### -field ScrollOffset

This member is reserved and should be set to zero.

Supported starting with Windows 8.

### -field DirtyRegions

[in] A <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_dirtyregions">D3DKMT_DIRTYREGIONS</a> structure that identifies the active rectangles (dirty regions) of the GDI surface.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_dirtyregions">D3DKMT_DIRTYREGIONS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_presenthistorytoken">D3DKMT_PRESENTHISTORYTOKEN</a>