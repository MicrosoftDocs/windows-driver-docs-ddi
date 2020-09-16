---
UID: NS:d3dkmdt._D3DKMT_MOVE_RECT
title: _D3DKMT_MOVE_RECT (d3dkmdt.h)
description: Provides information on a screen-to-screen move and a dirty rectangle copy operation.
old-location: display\d3dkmt_move_rect.htm
tech.root: display
ms.assetid: 2d9e0a8e-9485-427d-bdd0-2d89dec76a77
ms.date: 05/10/2018
keywords: ["D3DKMT_MOVE_RECT structure"]
ms.keywords: D3DKMT_MOVE_RECT, D3DKMT_MOVE_RECT structure [Display Devices], _D3DKMT_MOVE_RECT, d3dkmdt/D3DKMT_MOVE_RECT, display.d3dkmt_move_rect
req.header: d3dkmdt.h
req.include-header: 
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
req.typenames: D3DKMT_MOVE_RECT
f1_keywords:
 - _D3DKMT_MOVE_RECT
 - d3dkmdt/_D3DKMT_MOVE_RECT
 - D3DKMT_MOVE_RECT
 - d3dkmdt/D3DKMT_MOVE_RECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmdt.h
api_name:
 - D3DKMT_MOVE_RECT
---

# _D3DKMT_MOVE_RECT structure


## -description

Provides information on a screen-to-screen move and a dirty rectangle copy operation.

## -struct-fields

### -field SourcePoint

A <a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-tagpoint">POINT</a> structure that describes the source (<i>x, y</i>) point where the source rectangle is copied from.

### -field DestRect

A <a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-tagrect">RECT</a> structure that contains the destination rectangle where the dirty rectangle is copied to.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-tagpoint">POINT</a>



<a href="https://docs.microsoft.com/windows/win32/api/windef/ns-windef-tagrect">RECT</a>

