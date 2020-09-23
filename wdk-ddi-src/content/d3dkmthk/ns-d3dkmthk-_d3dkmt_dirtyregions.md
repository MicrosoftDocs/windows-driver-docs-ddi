---
UID: NS:d3dkmthk._D3DKMT_DIRTYREGIONS
title: _D3DKMT_DIRTYREGIONS (d3dkmthk.h)
description: The D3DKMT_DIRTYREGIONS structure describes active rectangles (dirty regions) of a surface.
old-location: display\d3dkmt_dirtyregions.htm
ms.assetid: 53565c01-9e6f-4ade-8c4a-2a4dbe7d48c7
ms.date: 05/10/2018
keywords: ["D3DKMT_DIRTYREGIONS structure"]
ms.keywords: D3DKMT_DIRTYREGIONS, D3DKMT_DIRTYREGIONS structure [Display Devices], OpenGL_Structs_a6113f9d-8ffc-4e75-8366-8329ad6c114b.xml, _D3DKMT_DIRTYREGIONS, d3dkmthk/D3DKMT_DIRTYREGIONS, display.d3dkmt_dirtyregions
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_DIRTYREGIONS is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DKMT_DIRTYREGIONS
f1_keywords:
 - _D3DKMT_DIRTYREGIONS
 - d3dkmthk/_D3DKMT_DIRTYREGIONS
 - D3DKMT_DIRTYREGIONS
 - d3dkmthk/D3DKMT_DIRTYREGIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_DIRTYREGIONS
---

# _D3DKMT_DIRTYREGIONS structure


## -description

The D3DKMT_DIRTYREGIONS structure describes active rectangles (dirty regions) of a surface.

## -struct-fields

### -field NumRects

[in] The number of dirty regions in the array that the <b>Rects</b> member specifies.

### -field Rects

[in] An array of <a href="/windows/win32/api/windef/ns-windef-tagrect">RECT</a> structures that specifies the dirty regions of a surface.

## -see-also

<a href="/windows/win32/api/windef/ns-windef-tagrect">RECT</a>