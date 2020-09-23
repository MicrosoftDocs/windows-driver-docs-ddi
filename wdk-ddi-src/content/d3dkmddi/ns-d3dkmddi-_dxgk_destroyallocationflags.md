---
UID: NS:d3dkmddi._DXGK_DESTROYALLOCATIONFLAGS
title: _DXGK_DESTROYALLOCATIONFLAGS (d3dkmddi.h)
description: The DXGK_DESTROYALLOCATIONFLAGS structure identifies how to release allocations.
old-location: display\dxgk_destroyallocationflags.htm
ms.assetid: 8f848d68-cef4-45a2-bdda-1bc8c9df6272
ms.date: 05/10/2018
keywords: ["DXGK_DESTROYALLOCATIONFLAGS structure"]
ms.keywords: DXGK_DESTROYALLOCATIONFLAGS, DXGK_DESTROYALLOCATIONFLAGS structure [Display Devices], DmStructs_acc32f8d-3d16-493e-be05-e739bc635bd0.xml, _DXGK_DESTROYALLOCATIONFLAGS, d3dkmddi/DXGK_DESTROYALLOCATIONFLAGS, display.dxgk_destroyallocationflags
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
targetos: Windows
tech.root: display
req.typenames: DXGK_DESTROYALLOCATIONFLAGS
f1_keywords:
 - _DXGK_DESTROYALLOCATIONFLAGS
 - d3dkmddi/_DXGK_DESTROYALLOCATIONFLAGS
 - DXGK_DESTROYALLOCATIONFLAGS
 - d3dkmddi/DXGK_DESTROYALLOCATIONFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_DESTROYALLOCATIONFLAGS
---

# _DXGK_DESTROYALLOCATIONFLAGS structure


## -description

The DXGK_DESTROYALLOCATIONFLAGS structure identifies how to release allocations.

## -struct-fields

### -field DestroyResource

A UINT value that specifies whether the resource that the <b>hResource</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a> structure specifies should be released along with allocations. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that DXGK_DESTROYALLOCATIONFLAGS contains that can hold a 32-bit value that identifies how to release allocations.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a>