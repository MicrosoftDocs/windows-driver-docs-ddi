---
UID: NS:d3dkmthk._D3DKMT_PRESENT_RGNS
title: _D3DKMT_PRESENT_RGNS (d3dkmthk.h)
description: Specifies dirty and move regions in a present operation.
old-location: display\d3dkmt_present_rgns.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_PRESENT_RGNS structure"]
ms.keywords: D3DKMT_PRESENT_RGNS, D3DKMT_PRESENT_RGNS structure [Display Devices], _D3DKMT_PRESENT_RGNS, d3dkmthk/D3DKMT_PRESENT_RGNS, display.d3dkmt_present_rgns
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_PRESENT_RGNS
f1_keywords:
 - _D3DKMT_PRESENT_RGNS
 - d3dkmthk/_D3DKMT_PRESENT_RGNS
 - D3DKMT_PRESENT_RGNS
 - d3dkmthk/D3DKMT_PRESENT_RGNS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_PRESENT_RGNS
 - D3DKMT_PRESENT_RGNS
---

# _D3DKMT_PRESENT_RGNS structure


## -description

Specifies dirty and move regions in a present operation.

## -struct-fields

### -field DirtyRectCount

The number of dirty rectangles.

### -field pDirtyRects

A pointer to an array of dirty rectangles (<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>s).

### -field MoveRectCount

The number of move rectangles.

### -field pMoveRects

A pointer to an array of move rectangles (<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>s).

## -see-also

<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>

