---
UID: NS:d3dkmddi._DXGK_DESCRIBEALLOCATIONFLAGS
title: _DXGK_DESCRIBEALLOCATIONFLAGS (d3dkmddi.h)
description: Used in the DXGKARG_DESCRIBEALLOCATION.Flags member to describe whether an existing allocation is being queried for its display mode.
old-location: display\dxgk_describeallocationflags.htm
ms.assetid: f5cab74a-19ce-45d1-9c6f-461a98c4506c
ms.date: 05/10/2018
keywords: ["DXGK_DESCRIBEALLOCATIONFLAGS structure"]
ms.keywords: DXGK_DESCRIBEALLOCATIONFLAGS, DXGK_DESCRIBEALLOCATIONFLAGS structure [Display Devices], _DXGK_DESCRIBEALLOCATIONFLAGS, d3dkmddi/DXGK_DESCRIBEALLOCATIONFLAGS, display.dxgk_describeallocationflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.typenames: DXGK_DESCRIBEALLOCATIONFLAGS
f1_keywords:
 - _DXGK_DESCRIBEALLOCATIONFLAGS
 - d3dkmddi/_DXGK_DESCRIBEALLOCATIONFLAGS
 - DXGK_DESCRIBEALLOCATIONFLAGS
 - d3dkmddi/DXGK_DESCRIBEALLOCATIONFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - DXGK_DESCRIBEALLOCATIONFLAGS
---

# _DXGK_DESCRIBEALLOCATIONFLAGS structure


## -description

Used in the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_describeallocation">DXGKARG_DESCRIBEALLOCATION</a>.<b>Flags</b> member to describe whether an existing allocation is being queried for its display mode.

## -struct-fields

### -field CheckDisplayMode

[in] This member is reserved.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

[in] This member is reserved and should be set to zero. 

Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

[in] A member in the union that <b>DXGK_DESCRIBEALLOCATIONFLAGS</b> contains that can hold a 32-bit value that identifies the type of allocation.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_describeallocation">DXGKARG_DESCRIBEALLOCATION</a>