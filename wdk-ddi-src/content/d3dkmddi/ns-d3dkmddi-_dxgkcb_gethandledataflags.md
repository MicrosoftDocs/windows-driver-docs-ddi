---
UID: NS:d3dkmddi._DXGKCB_GETHANDLEDATAFLAGS
title: DXGKCB_GETHANDLEDATAFLAGS (d3dkmddi.h)
description: The DXGKCB_GETHANDLEDATAFLAGS structure indicates if allocations belong to a resource.
old-location: display\dxgkcb_gethandledataflags.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_GETHANDLEDATAFLAGS structure"]
ms.keywords: DXGKCB_GETHANDLEDATAFLAGS, DXGKCB_GETHANDLEDATAFLAGS structure [Display Devices], DmStructs_a0288df8-0513-4823-9445-cd86ff45a186.xml, _DXGKCB_GETHANDLEDATAFLAGS, d3dkmddi/DXGKCB_GETHANDLEDATAFLAGS, display.dxgkcb_gethandledataflags
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
req.typenames: DXGKCB_GETHANDLEDATAFLAGS
f1_keywords:
 - _DXGKCB_GETHANDLEDATAFLAGS
 - d3dkmddi/_DXGKCB_GETHANDLEDATAFLAGS
 - DXGKCB_GETHANDLEDATAFLAGS
 - d3dkmddi/DXGKCB_GETHANDLEDATAFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKCB_GETHANDLEDATAFLAGS
 - DXGKCB_GETHANDLEDATAFLAGS
---

# DXGKCB_GETHANDLEDATAFLAGS structure

## -description

The **DXGKCB_GETHANDLEDATAFLAGS** structure indicates whether allocations belong to a resource.

## -struct-fields

### -field DeviceSpecific

A UINT value that specifies whether allocations belong to a resource. If this member is set, the allocations belong to a resource.

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit **Value** member to zeros.

### -field Value

The 32-bit value that indicates all of the flags set in the union.

## -see-also

[**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md)
