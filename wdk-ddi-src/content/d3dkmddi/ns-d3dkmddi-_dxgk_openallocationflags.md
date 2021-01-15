---
UID: NS:d3dkmddi._DXGK_OPENALLOCATIONFLAGS
title: _DXGK_OPENALLOCATIONFLAGS (d3dkmddi.h)
description: The DXGK_OPENALLOCATIONFLAGS structure identifies the operation to perform for allocations.
old-location: display\dxgk_openallocationflags.htm
ms.date: 05/10/2018
keywords: ["DXGK_OPENALLOCATIONFLAGS structure"]
ms.keywords: DXGK_OPENALLOCATIONFLAGS, DXGK_OPENALLOCATIONFLAGS structure [Display Devices], DmStructs_3b5228f0-93fa-434a-b2ca-9007c372d9ed.xml, _DXGK_OPENALLOCATIONFLAGS, d3dkmddi/DXGK_OPENALLOCATIONFLAGS, display.dxgk_openallocationflags
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
req.typenames: DXGK_OPENALLOCATIONFLAGS
f1_keywords:
 - _DXGK_OPENALLOCATIONFLAGS
 - d3dkmddi/_DXGK_OPENALLOCATIONFLAGS
 - DXGK_OPENALLOCATIONFLAGS
 - d3dkmddi/DXGK_OPENALLOCATIONFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_OPENALLOCATIONFLAGS
 - DXGK_OPENALLOCATIONFLAGS
---

# _DXGK_OPENALLOCATIONFLAGS structure


## -description

The DXGK_OPENALLOCATIONFLAGS structure identifies the operation to perform for allocations.

## -struct-fields

### -field Create

A UINT value that specifies whether allocations should be created. If this member is not set, the allocations are opened. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b>= member (0x00000001).

### -field ReadOnly

A UINT value that specifies whether the allocation can only be read from. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b>= member (0x00000002).

Supported starting with Windows 8.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that DXGK_OPENALLOCATIONFLAGS contains that can hold a 32-bit value that identifies the operation to perform for allocations.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_openallocation">DXGKARG_OPENALLOCATION</a>

